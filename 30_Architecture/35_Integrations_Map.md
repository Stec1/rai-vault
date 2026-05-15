# Integrations Map

This note catalogs external services RAi depends on, including current operating status.

## Service map
| Service | Role | Status |
|---|---|---|
| Vercel (`rai-web`) | Canonical production frontend origin and same-origin `/api/...` entrypoint for browser traffic. | active |
| Vercel API proxy (`API_PROXY_ORIGIN`) | Proxies same-origin `/api/...` calls from frontend origin to Railway API origin. | active |
| Railway (`@rai/api`) | Canonical production API runtime origin (`https://raiapi-production.up.railway.app`). | active |
| Railway (`@rai/web`) | Present in Railway project but not canonical production frontend runtime. | active (non-canonical frontend path) |
| PostgreSQL 15+ | Primary relational database system of record. | active |
| Redis 7.x | Rate limiting and ephemeral auth/control state. | active |
| Better Auth 1.x | Authentication, session issuance, and identity workflows (email/password baseline). | active |
| Prisma adapter (Better Auth) | Persistence adapter for auth session/account/verification data. | active |
| BullMQ 4.x | Async jobs for Visual Signature and Publication formatting workloads. | planned |
| OpenAI GPT-4o | Visual Signature generation and Publication formatting intelligence. | planned |
| Stripe | Credits, checkout, and subscription billing lifecycle. | planned (test mode until launch) |
| Resend | Transactional email delivery and notification pathways. | deferred |
| Google OAuth provider | Social login pathway in auth stack. | deferred |
| Cloudflare R2 | Object/file storage for generated and uploaded assets. | planned |
| PostHog | Product analytics and usage instrumentation. | planned |
| Sentry | Error monitoring, tracing, and operational alerting. | planned |

## Status notes
- Canonical production traffic path: browser on `https://rai-web-one.vercel.app` → same-origin `/api/...` on Vercel → Railway API (`https://raiapi-production.up.railway.app`).
- `API_PROXY_ORIGIN` is set to `https://raiapi-production.up.railway.app`.
- Recovery chain corrected env/runtime alignment for Railway `@rai/api` and stabilized signup/login + `/api/me` via same-origin proxy.
- OAuth, Resend, and password reset remain out of active baseline.

## See also in vault
- [[31_Infrastructure_State]]
- [[34_Env_And_Secrets_Map]]
- [[36_Deployment_State]]
- [[ISSUE-08_Recovery_Notes]]

## See also in repo
- `docs/architecture.md`
