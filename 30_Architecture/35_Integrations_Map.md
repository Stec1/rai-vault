# Integrations Map

This note catalogs external services RAi depends on, including current operating status.

## Service map
| Service | Role | Status |
|---|---|---|
| Vercel | Web application deployment target. | planned |
| Railway | API/workers hosting plus managed PostgreSQL and Redis baseline. | active |
| PostgreSQL 15+ | Primary relational database system of record. | active |
| Redis 7.x | Cache, ephemeral state, and queue backing store. | active |
| BullMQ 4.x | Async jobs for Visual Signature and Publication formatting workloads. | planned |
| Better Auth 1.x | Authentication, session issuance, and identity workflows. | pending ([[ISSUE-04]]) |
| OpenAI GPT-4o | Visual Signature generation and Publication formatting intelligence. | planned |
| Stripe | Credits, checkout, and subscription billing lifecycle. | planned (test mode until launch) |
| Resend | Transactional email delivery and notification pathways. | planned |
| Cloudflare R2 | Object/file storage for generated and uploaded assets. | planned |
| PostHog | Product analytics and usage instrumentation. | planned |
| Sentry | Error monitoring, tracing, and operational alerting. | planned |

## Status notes
- Only infrastructure-baseline integrations (Railway, PostgreSQL, Redis) are currently active.
- All other integrations remain planned or pending implementation milestones.

## See also in vault
- [[31_Infrastructure_State]]
- [[34_Env_And_Secrets_Map]]
- [[36_Deployment_State]]

## See also in repo
- `docs/architecture.md`
