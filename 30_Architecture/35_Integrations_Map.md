# Integrations Map

This note catalogs external services RAi depends on, including current operating status.

## Service map
| Service | Role | Status |
|---|---|---|
| Vercel | Web application deployment target and frontend auth/session client behavior. | active |
| Railway | API hosting plus managed PostgreSQL and Redis; production auth runtime context. | active |
| PostgreSQL 15+ | Primary relational database system of record. | active |
| Redis 7.x | Rate limiting and ephemeral auth/control state. | active |
| Better Auth 1.x | Authentication, session issuance, and identity workflows (email/password in Phase 1). | active |
| Prisma adapter (Better Auth) | Persistence adapter for auth session/account/verification data. | active |
| BullMQ 4.x | Async jobs for Visual Signature and Publication formatting workloads. | planned |
| OpenAI GPT-4o | Visual Signature generation and Publication formatting intelligence. | planned |
| Stripe | Credits, checkout, and subscription billing lifecycle. | planned (test mode until launch) |
| Resend | Transactional email delivery and notification pathways. | deferred (not part of ISSUE-04 Phase 1) |
| Google OAuth provider | Social login pathway in auth stack. | deferred (Phase 2) |
| Cloudflare R2 | Object/file storage for generated and uploaded assets. | planned |
| PostHog | Product analytics and usage instrumentation. | planned |
| Sentry | Error monitoring, tracing, and operational alerting. | planned |

## Status notes
- Current production auth path runs across Vercel web + Railway API with Better Auth sessions.
- Railway production recovery after ISSUE-04 required runtime/start-path alignment, Prisma `importFileExtension = "js"`, and auth env var correction.
- OAuth, Resend, and password reset are not active in current baseline.

## See also in vault
- [[31_Infrastructure_State]]
- [[34_Env_And_Secrets_Map]]
- [[36_Deployment_State]]

## See also in repo
- `docs/architecture.md`
