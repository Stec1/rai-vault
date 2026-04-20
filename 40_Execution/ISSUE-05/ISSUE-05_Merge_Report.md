# Merge Report: ISSUE-05 — Observatory Identity Logic

## Date
2026-04-20

## What Changed
- ISSUE-05 was merged and deployed.
- Public observatory name availability check endpoint was added: `GET /api/v1/observatories/check/:name`.
- Shared naming/display utilities were added for reserved-name handling, observatory-name normalization + format validation, and display-name derivation from email.
- `/api/me` response was extended with `observatory: { id, name } | null`.
- Post-login redirect logic was updated to route users with an observatory to `/dashboard`, and users without one to `/create`.

## Why It Changed
- To establish a stable observatory identity baseline prior to observatory creation and control panel flows.
- To centralize naming and display derivation behavior in shared utilities.

## Files / Areas Touched (high level)
- Observatories check route module.
- Shared utility modules for reserved names, observatory name handling, and display-name derivation.
- Authenticated user context route (`/api/me`).
- Post-login redirect/routing logic.

## Validation Status
- Merge: succeeded.
- Deploy: succeeded.
- Availability endpoint: active with 30/min per-IP rate limit.
- `/api/me` observatory field: active.
- Redirect behavior: active (`/dashboard` vs `/create`).

## Risks
- Observatory creation and management flows are not yet delivered by design.
- Future issues must preserve utility-level normalization/validation consistency when adding creation or CRUD flows.

## Next Action
- Await founder selection of the next implementation issue (ISSUE-06 or ISSUE-07).

## What Must Be Recorded in Vault
- ISSUE-05 is completed, merged, and deployed.
- Observatory availability check is active at `GET /api/v1/observatories/check/:name`.
- Shared identity utilities (reserved names, observatory name normalize/validate, display-name derivation) are active.
- `/api/me` includes `observatory: { id, name } | null`.
- Post-login redirect rule is active (`/dashboard` when observatory exists, `/create` otherwise).

## Vault Links
- [[00_Current_State]]
- [[01_Next_Action]]
- [[03_MOC_Execution]]
- [[33_API_Surface]]
