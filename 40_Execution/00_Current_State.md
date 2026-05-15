# Current State

## Snapshot (2026-05-15)

### Foundation + Auth Baseline — Completed
- ISSUE-00 through ISSUE-07 are completed and remain closed.
- SI target architecture remains accepted as post-MVP target only (no SI scope pull-in to active MVP execution).

### Explore Foundation + Redesign Chain — Completed
- ISSUE-08 completed as technical foundation:
  - `/api/v1/domains` activated.
  - initial `/explore` map/topology baseline landed.
  - original PNG-node + mini-map visual direction was superseded by ISSUE-08R.
- ISSUE-08R completed:
  - `/explore` rebuilt as SVG MVP topology (RA center + 7 domain nodes + RA→Domain connections).
  - info-panel interaction and auth-aware CTA integrated.
  - post-auth no-observatory destination switched to `/explore`.
- ISSUE-08R follow-ups completed:
  - ISSUE-08R.1 routing/chrome correction,
  - ISSUE-08R.2 pan/zoom hardening,
  - ISSUE-08R.3 PNG cleanup (DL-27),
  - ISSUE-08R.4 canonical TopBar/routing cleanup (DL-28).

### Canonical UX/Routing Baseline (post ISSUE-08R.4)
- `/` Start Page renders for all visitors.
- `/explore` is public discovery and primary post-auth topology surface for authenticated users without observatory.
- `/create` remains CTA destination from Explore for auth-no-observatory users (placeholder/early surface).
- `/dashboard` remains destination for authenticated users with observatory (placeholder/early surface).
- TopBar canonical roles (DL-28):
  - logo → `/`
  - guest → About / Log in / Get Started
  - authNoObservatory → Explore / About / Sign out
  - authWithObservatory → Explore / Dashboard / Sign out
- PNG domain objects are removed from MVP visual system (DL-27).

### Production Runtime Stability — Recovered and Active
- Same-origin Vercel API proxy is stable (`/api/...` via Vercel to Railway API).
- `/api/health` returns 200 via proxy.
- `/api/v1/domains` returns 7 domains via proxy.
- Signup/login sessions and `/api/me` auth check are operational through same-origin flow.
- Recovery details are recorded in [[ISSUE-08_Recovery_Notes]].

### Deferred / Not Completed Yet
- Full Create Observatory flow implementation is not recorded as complete.
- Dashboard is not recorded as complete.
- Observatory graph nodes on `/explore` are not recorded as implemented.
- Three.js/R3F topology runtime is not recorded as active implementation.

## Working Reference
Use this note before planning, prompting, or coding.
Check [[01_Next_Action]] for the immediate executable step.
Check [[Decision_Index]] for recent decisions.
