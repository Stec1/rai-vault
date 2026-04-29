# Current State

## Snapshot (2026-04-29)

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

### Observatory Identity Baseline — Completed (ISSUE-05)
- ISSUE-05 is completed, merged, and deployed.
- Observatory name availability endpoint active: GET /api/v1/observatories/check/:name (rate-limited).
- Shared utilities active: reserved names, observatory name normalize + format validation, displayName derivation from email.
- /api/me now returns observatory: { id, name } | null.
- Post-login redirect rule in place: observatory present → /dashboard, absent → /create.

### Start Page Baseline — Completed (ISSUE-06)
- ISSUE-06 is completed and merged (initial implementation + visual refinements).
- Public Start Page is active at `/`.
- Auth redirect behavior is preserved:
  - unauthenticated users see Start Page,
  - authenticated + no observatory → `/create`,
  - authenticated + observatory → `/dashboard`.
- UI foundation now includes semantic design tokens, global styles baseline, and typography stack (Space Grotesk / Inter / JetBrains Mono).
- Start Page structure includes TopBar, Hero, How it Works, Domain showcase, CTA, Footer.
- Refinements landed: transparent PNG domain objects (no card/chip/panel treatment), RA hero object on desktop/laptop/tablet only, hidden on mobile, no visible “RA” label.
- Mobile presentation remains typography-first.

### Not Included Yet (Deferred)
- Google OAuth
- Resend integration
- Password reset flows
- SI target architecture activation in MVP execution (accepted as post-MVP target only)

### Blockers / Risks
- None currently recorded in vault execution notes.
- SI target acceptance remains unchanged and post-MVP; active MVP path continues without SI scope pull-in.

## Working Reference
Use this note before planning, prompting, or coding.
Check [[01_Next_Action]] for the immediate executable step.
Check [[Decision_Index]] for recent decisions.
