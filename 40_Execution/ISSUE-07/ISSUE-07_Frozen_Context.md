# ISSUE-07 Frozen Context

## Scope Lock (pre-implementation)
ISSUE-07 scope is limited to **About + Auth Screens** for MVP public/auth UX alignment.

### In scope
- Public About page at `/about` with MVP-facing editorial copy.
- Auth pages at `/login` and `/signup` using existing Better Auth email/password flow.
- Public legal placeholders at `/privacy` and `/terms`.
- Redirect handling from login/signup paths based on `/api/me` observatory state.

### Explicitly out of scope
- Google OAuth UI/actions (deferred to ISSUE-04 Phase 2).
- Password reset screen/flow.
- Email verification screen/flow.
- SI target architecture activation in MVP execution.

## Founder/Product decisions already in force
- MVP auth entry remains email/password only.
- Public copy must remain MVP editorial and avoid SI-only terminology.
- ISSUE-06 Start Page behavior and existing layout shell (TopBar/Footer) are preserved.
- Design language remains solid editorial cards with semantic tokens (no glassmorphism/glow/heavy shadow).

## Dependency baseline
- ISSUE-04 Phase 1 completed (auth core + `/api/me`).
- ISSUE-05 completed (observatory-aware redirect logic contract).
- ISSUE-06 completed (public Start Page baseline and style direction).
