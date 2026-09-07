---
name: cvent-registration-onsite-check-in
description: Check an attendee in at a Cvent event or session, print a badge, and undo a mistaken check-in.
generated: '2026-09-07'
method: generated
source: openapi/cvent-registration-events-api-openapi.yml, openapi/cvent-registration-attendees-api-openapi.yml, openapi/cvent-registration-seating-api-openapi.yml
api: Cvent Registration REST API
base_url: https://api-platform.cvent.com/ea
operations:
  - listAttendeesPostFilter
  - eventCheckIn
  - deleteEventCheckIn
  - sessionCheckIn
  - updateSessionCheckIn
  - deleteSessionAttendance
  - listSessionsAttendance
  - postBadge
  - getBadge
  - updateBadge
---

# On-site check-in and badging

## Event check-in

1. **Find the attendee.** `listAttendeesPostFilter` (`POST /attendees/filter`) scoped to the event.
2. **Check in.** `eventCheckIn` (`POST /events/{id}/check-in`).
3. **Undo a mistake.** `deleteEventCheckIn` (`DELETE /events/{id}/check-in/{attendeeId}`).
   This is a real reversal path. Cvent publishes **no window** for it — do not claim one.

## Session check-in

- `sessionCheckIn` (`POST /sessions/{id}/check-in`) to check in.
- `updateSessionCheckIn` (`PUT /sessions/{id}/check-in`) to amend.
- `deleteSessionAttendance` (`DELETE /sessions/{id}/attendance/{attendeeId}`) to undo.
- `listSessionsAttendance` (`GET /sessions/attendance`) to read the current state.

## Badges

`postBadge` (`POST /events/{id}/badges`), `getBadge` (`GET /events/{id}/badges`),
`getBadgesPostFilters` (`POST /events/{id}/badges/filter`), `updateBadge`
(`PUT /events/{id}/badges/{badgeId}`).

Badge printing failures surface as `BadgePrintJobErrorCode`: `BadgeNotFound`, `BadgeRenderIssue`,
`Connection`, `PrinterError`, `AttendeeDataMissing`, `Unknown`. `Connection` and `PrinterError` are
hardware conditions — retry them; `AttendeeDataMissing` and `BadgeNotFound` are data conditions —
fix the record first, retrying will not help.

## On-site rate reality

The on-site desk is exactly where the daily quota bites. Free is **1,000 calls/day at 2/s**;
Standard **15,000/day at 10/s**; Premium **500,000/day at 25/s**. Read the account's tier with
`getUsageTier` (`GET /usage/tier`) and current consumption with `getUsage` (`GET /usage`) BEFORE a
check-in shift, not during one. Every request counts, including the ones that 429.

There is **no idempotency key**. A double-tapped check-in button is a second real call. Read the
attendee's state back rather than firing again.
