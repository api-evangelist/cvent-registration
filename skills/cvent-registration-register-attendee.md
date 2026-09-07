---
name: cvent-registration-register-attendee
description: Register a contact as an attendee on a Cvent event, verify the registration, and cancel it safely if needed.
generated: '2026-09-07'
method: generated
source: openapi/cvent-registration-attendees-api-openapi.yml, openapi/cvent-registration-events-api-openapi.yml
api: Cvent Registration REST API
base_url: https://api-platform.cvent.com/ea
operations:
  - getEvents
  - getEventById
  - listRegistrationTypes
  - listAdmissionItems
  - listContacts
  - createContacts
  - createAttendee
  - getAttendeeById
  - listAttendeesPostFilter
  - updateAttendee
---

# Register an attendee on a Cvent event

Every operationId below exists in `openapi/cvent-registration-*-openapi.yml`, which is cut from
Cvent's own published contract. Do not invent endpoints.

## Before you start

1. Get a token: `POST /ea/oauth2/token` with `Authorization: Basic base64(client_id:client_secret)`,
   `Content-Type: application/x-www-form-urlencoded`, `grant_type=client_credentials`.
   The token lives **3600 seconds**. Send it as `Authorization: Bearer {access_token}`.
2. Pick the right host. `https://api-platform.cvent.com/ea` for North American accounts,
   `https://api-platform-eur.cvent.com/ea` for European. There is no endpoint that tells you which —
   you must know the account's data centre.
3. Request only the scopes you need. This flow needs at least `event/attendees:write`,
   `event/attendees:read`, `event/contacts:read` and `event/events:read`.

## Steps

1. **Find the event.** `getEvents` (`GET /events`), or `getEventsPostFilters`
   (`POST /events/filter`) when the filter is long. Confirm with `getEventById`.
2. **Read what the event will accept.** `listRegistrationTypes` (`GET /events/{id}/registration-types`)
   and `listAdmissionItems` (`GET /admission-items`). A registration that names a registration type
   the event does not have comes back `400 Bad request`.
3. **Resolve the person.** `listContacts` (`GET /contacts`) with
   `filter=emailAddress eq 'person@example.com'`, or `listContactsPostFilters` for a batch.
   Create them with `createContacts` (`POST /contacts`) only if there is no match — creating a
   duplicate contact is not reversible in one call.
4. **Register.** `createAttendee` (`POST /attendees`).
5. **Verify.** `getAttendeeById` (`GET /attendees/{id}`), or `listAttendeesPostFilter`
   (`POST /attendees/filter`) scoped to the event.

## Retry rules — read this before you retry anything

**Cvent publishes no idempotency mechanism.** There is no `Idempotency-Key` header on any of the
138 mutating registration operations. If `createAttendee` times out you cannot safely repeat it.

- On a timeout or connection error: **do not re-POST.** Call `listAttendeesPostFilter` filtered on
  the contact and the event, and only register again if nothing came back.
- `429` means one of two different things and the status code does not tell you which. Read the
  message body: `Too Many Requests` is per-second throttling — back off (2s, 4s, 8s, 16s, stop at
  ~5 attempts, matching Cvent's own SDK policy) and retry. `Limit Exceeded` is the daily quota —
  stop; retrying burns quota, and even the 429 itself counted against it.
- There is no `Retry-After` header. Use the fixed backoff above.
- `403` is a scope problem, not a data problem: compare the operation's `security[].scopes` in the
  spec against what you asked for at token time.

## Cancelling a registration

There is **no cancel operation**. Cancellation is a status transition: `updateAttendee`
(`PUT /attendees/{id}`) setting `status` to `Cancelled`. The valid `AttendeeStatus` values are
`No Response`, `Accepted`, `Declined`, `Visited`, `Waitlisted`, `Cancelled`, `Pending Approval`,
`Denied Approval`; Cvent documents `Pending Approval -> Cancelled` as supported.

**Cvent states no window for this.** Do not tell a user a cancellation deadline — the docs do not
publish one. See `conventions/cvent-registration-conventions.yml`.

## Pagination

Every list is cursor-paged: pass `limit` and `token`, read `paging.nextToken` from the response,
stop when `nextToken` is absent. An empty `data` array on the last page is normal and expected.
