# ISSUE-05 Result

## Status
Completed (merged and deployed).

## What Landed
- `GET /api/v1/observatories/check/:name` availability endpoint is active (rate-limited 30/min per IP).
- Shared `reserved-names` utility landed with the extended reserved list.
- Shared observatory-name utility landed with normalization + format validation logic.
- Shared display-name utility landed to derive `displayName` from email.
- `/api/me` now returns `observatory: { id, name } | null`.
- Post-login redirect rule is active: observatory present → `/dashboard`, absent → `/create`.

## Explicitly Out of Scope (Not Landed)
- Observatory creation flow (ISSUE-11).
- Control Panel UI (ISSUE-12).
- Observatory CRUD endpoints beyond the availability check endpoint.

## Final Validated Outcome
- Availability check is operational.
- `/api/me` returns the observatory field.
- Post-login redirect logic is in place.

## Vault Links
- [[00_Current_State]]
- [[01_Next_Action]]
- [[03_MOC_Execution]]
- [[33_API_Surface]]
