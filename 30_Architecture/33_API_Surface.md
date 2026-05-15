# API Surface

This note is an operating-level map of API route groups and intended behavior. Implementation lives in `apps/api/src/routes/` in the RAi product repo.

## Route group map
| Route group | Purpose | Status |
|---|---|---|
| `/api/health` | Liveness and runtime health check through same-origin Vercel proxy path. | active (production-validated via proxy) |
| Better Auth runtime endpoints | Authentication/session handling via Better Auth runtime mount, consumed through same-origin `/api/...` frontend path. | active |
| `/api/me` | Returns authenticated user context plus observatory `{ id, name } \| null`; used for auth-aware routing checks. | active |
| `/api/v1/auth` | Versioned auth group in product model. | not active as standalone group (Better Auth runtime + `/api/me` are active) |
| `/api/v1/observatories` | Observatory identity operations including public name availability check; broader CRUD/ownership operations remain pending. | partial (check endpoint active; CRUD pending) |
| `/api/v1/domains` | Domain read operations for Explore topology and discovery surfaces. | active (returns 7 seeded domains in production via proxy) |
| `/api/v1/systems` | System CRUD and related lifecycle operations. | pending |
| `/api/v1/publications` | Publication CRUD and publication formatting workflows. | pending |
| `/api/v1/upvotes` | Create/remove publication upvotes. | pending |
| `/api/v1/search` | Full-text search across core content objects. | pending |
| `/api/v1/generate` | Visual Signature generation and formatting queue entrypoints. | pending |
| `/api/v1/visits` | Observatory visit tracking and aggregation intake. | pending |
| `/api/v1/payments` | Stripe checkout session creation and webhook handling. | pending |

## Status notes
- Active API baseline includes `/api/health`, Better Auth runtime endpoints, `/api/me`, and `/api/v1/domains`.
- Same-origin API path is browser `→ /api/...` on Vercel frontend origin, proxying to Railway API origin.
- Auth signup/login and `/api/me` session checks are production-valid through same-origin proxy.
- OAuth and password reset endpoints remain deferred and not active.

## See also in vault
- [[32_Database_Model]]
- [[35_Integrations_Map]]
- [[36_Deployment_State]]
- [[03_MOC_Execution]]

## See also in repo
- `docs/architecture.md`
- `apps/api/src/routes/`
