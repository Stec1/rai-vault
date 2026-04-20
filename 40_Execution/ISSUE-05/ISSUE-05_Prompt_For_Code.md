# ISSUE-05 Prompt for Code

Historical placeholder — ISSUE-05 execution already completed.

## Original implementation scope
- Deliver `GET /api/v1/observatories/check/:name` with rate limiting.
- Add shared reserved-name and observatory-name utilities (normalize + format validation).
- Add display-name derivation utility from email.
- Extend `/api/me` to return `observatory: { id, name } | null`.
- Apply post-login redirect rule: observatory present → `/dashboard`, absent → `/create`.

## Out of scope
- Observatory creation flow.
- Control Panel UI.
- Observatory CRUD beyond name availability check.
