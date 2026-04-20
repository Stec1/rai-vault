# API Surface

This note is an operating-level map of API route groups and intended behavior. Implementation lives in `apps/api/src/routes/` in the RAi product repo.

## Route group map
| Route group | Purpose | Status |
|---|---|---|
| `/api/health` | Liveness and baseline runtime health check. | active (verified in [[ISSUE-02]]) |
| Better Auth runtime endpoints | Authentication/session handling served by Better Auth runtime mount. | active (ISSUE-04 Phase 1) |
| `/api/me` | Returns authenticated user context plus observatory `{ id, name } \| null` (ISSUE-05). | active (ISSUE-04 Phase 1 + ISSUE-05 extension) |
| `/api/v1/auth` | Versioned auth group in product model. | not active as standalone group (Better Auth runtime + `/api/me` are active) |
| `/api/v1/observatories` | Observatory identity operations including public name availability check; broader CRUD/ownership operations remain pending. | partial (check endpoint active in ISSUE-05; CRUD pending) |
| `/api/v1/domains` | Domain read and filter operations. | pending |
| `/api/v1/systems` | System CRUD and related lifecycle operations. | pending |
| `/api/v1/publications` | Publication CRUD and publication formatting workflows. | pending |
| `/api/v1/upvotes` | Create/remove publication upvotes. | pending |
| `/api/v1/search` | Full-text search across core content objects. | pending |
| `/api/v1/generate` | Visual Signature generation and formatting queue entrypoints. | pending |
| `/api/v1/visits` | Observatory visit tracking and aggregation intake. | pending |
| `/api/v1/payments` | Stripe checkout session creation and webhook handling. | pending |

## Status notes
- Active API baseline includes `/api/health`, Better Auth runtime endpoints, and protected `/api/me`.
- ISSUE-05 added public name availability check under `/api/v1/observatories/check/:name` (rate-limited 30/min per IP) and extended `/api/me` with observatory field.
- Auth Phase 1 is email/password only.
- OAuth and password reset endpoints are deferred to auth Phase 2 and not active.

## See also in vault
- [[32_Database_Model]]
- [[35_Integrations_Map]]
- [[03_MOC_Execution]]

## See also in repo
- `docs/architecture.md`
- `apps/api/src/routes/`
