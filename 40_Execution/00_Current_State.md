# Current State

## Snapshot (2026-04-20)

### Foundation Phase — Completed
- ISSUE-00: Documentation rewrite — completed 2026-04-15
- ISSUE-01: Monorepo scaffold + infrastructure baseline — completed 2026-04-15
- ISSUE-02: Deployment + health readiness (PostgreSQL, Redis, `/api/health`) — completed 2026-04-15
- ISSUE-03: Database schema + seed — completed 2026-04-16

### Auth Phase Baseline — Completed (ISSUE-04 Phase 1)
- ISSUE-04 Phase 1 is completed, merged, and deployed.
- Implementation baseline now includes:
  - Better Auth with Prisma adapter
  - Auth persistence tables: Session, Account, Verification
  - Email/password authentication (only)
  - Protected route: `/api/me`
  - Redis-based auth rate limiting
  - Railway production runtime boot fixes applied and stable

### Not Included Yet (Deferred)
- Google OAuth
- Resend integration
- Password reset flows

### Observatory Identity Baseline — Completed (ISSUE-05)
- ISSUE-05 is completed, merged, and deployed.
- Observatory name availability endpoint active: GET /api/v1/observatories/check/:name (rate-limited).
- Shared utilities active: reserved names, observatory name normalize + format validation, displayName derivation from email.
- /api/me now returns observatory: { id, name } | null.
- Post-login redirect rule in place: observatory present → /dashboard, absent → /create.

### Blockers / Risks
- None currently recorded in vault execution notes
- 2026-04-28: SI accepted as target architecture (see [[DL-008]], [[38_SI_Target_Bridge]]). Active MVP execution unchanged; ISSUE-06 is completed in the product repo, ISSUE-06 vault closure remains separate, and ISSUE-07 is the next implementation issue.

## Working Reference
Use this note before planning, prompting, or coding.
Check [[01_Next_Action]] for the immediate executable step.
Check [[Decision_Index]] for recent decisions.
