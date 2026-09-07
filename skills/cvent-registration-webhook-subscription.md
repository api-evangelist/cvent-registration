---
name: cvent-registration-webhook-subscription
description: Subscribe to Cvent registration events by webhook, and reconcile against the REST change-history API when a delivery is missed.
generated: '2026-09-07'
method: generated
source: openapi/cvent-registration-webhooks-api-openapi.yml, asyncapi/cvent-registration-webhooks.yml
api: Cvent Registration Webhooks
base_url: https://api-platform.cvent.com/ea
operations:
  - ListContactHooks
  - createContactHook
  - updateContactHook
  - deleteContactHook
  - getChangeHistoryForASpecificContact
---

# Subscribe to Cvent registration events

Cvent publishes **41 documented webhook messages** across attendees, attendee-emails, contacts,
event-sessions, event-speakers, events, meeting-requests and a manual-sync group. The full
catalogue with a docs URL per message is in `asyncapi/cvent-registration-webhooks.yml`.
Cvent does **not** publish an AsyncAPI document — treat the per-message docs pages as the schema.

## Contact hooks (API-managed)

- `ListContactHooks` (`GET /contacts/hooks`)
- `createContactHook` (`POST /contacts/hooks`)
- `updateContactHook` (`PUT /contacts/hooks/{id}`)
- `deleteContactHook` (`DELETE /contacts/hooks/{id}`)

Needs `account/hooks:read`, `account/hooks:write`, `account/hooks:delete`.

## Event, session and speaker webhooks (UI-configured)

These are **not** API-managed. They are configured per event in the Cvent UI — see the Event Setup
and Session Setup guides on the developer portal. An agent cannot subscribe to
`attendees/registered-for-event` programmatically; a human enables it on the event.

## The registration messages that matter

`attendees/registered-for-event`, `attendees/registration-modified`,
`attendees/registration-cancelled`, `attendees/abandons-registration`,
`attendees/registered-for-session`, `attendees/session-registration-cancelled`,
`attendees/substituted-into-event-registration`, `attendees/marked-as-no-show`,
`attendees/invitee-guest-order-created`.

## Reconciliation — assume you will miss deliveries

Cvent documents no delivery guarantee, no signature scheme and no replay endpoint on the webhook
pages. Pair every subscription with a polling reconciliation:

- `getChangeHistoryForASpecificContact` (`GET /contacts/{contactId}/history`) for one record.
- The `after` / `before` query parameters on supported collections bound a change window —
  `after` is the lower time limit, `before` the upper. Keep a watermark and sweep periodically.
  See https://developers.cvent.com/docs/rest-api/guides/managing-change-history.
- The `manual/*` message group exists precisely for operator-triggered resync.

All timestamps are ISO 8601 UTC with a `Z` suffix — **except** custom-field/question date-times and
meeting-request-form event dates, which Cvent documents as being in event-local time with no `Z`.
Do not assume UTC on those.
