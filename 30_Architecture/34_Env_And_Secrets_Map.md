# Environment and Secrets Map

This note inventories environment variable names and purpose at an operating level. Real values live only in Railway, Vercel, or local runtime stores such as `.env.local`.

## Resolution priority
- Railway environment variables override all lower layers.
- Vercel environment variables apply where Railway is not the serving runtime.
- `.env.local` is local-only fallback for development.

## Naming conventions
- `NEXT_PUBLIC_*` values are intentionally exposed to frontend bundles.
- `*_URL` values represent connection strings or base endpoints.
- `*_KEY` values represent API keys/tokens.
- `*_SECRET` values represent signing or webhook secrets.

## Variable inventory
| Variable name | Purpose | Scope |
|---|---|---|
| DATABASE_URL | PostgreSQL connection. | backend |
| REDIS_URL | Redis connection. | backend |
| BETTER_AUTH_SECRET | Session signing and auth cryptographic secret. | backend |
| BETTER_AUTH_URL | Authentication service base URL. | both |
| GOOGLE_CLIENT_ID / GOOGLE_CLIENT_SECRET | Google OAuth provider credentials. | backend |
| OPENAI_API_KEY | GPT-4o API access. | backend |
| STRIPE_SECRET_KEY / STRIPE_WEBHOOK_SECRET | Stripe API and webhook signature validation. | backend |
| NEXT_PUBLIC_STRIPE_PUBLISHABLE_KEY | Stripe Checkout initialization key for frontend. | frontend |
| RESEND_API_KEY | Transactional email provider access. | backend |
| CLOUDFLARE_R2_* | Cloudflare R2 storage credentials/configuration. | backend |
| POSTHOG_KEY / NEXT_PUBLIC_POSTHOG_KEY | Product analytics ingestion keys. | both |
| SENTRY_DSN / NEXT_PUBLIC_SENTRY_DSN | Error tracking DSNs for server/client telemetry. | both |

## Policy
- Never hardcode secrets in source files.
- Never commit real secret values to git.

## See also in vault
- [[31_Infrastructure_State]]
- [[35_Integrations_Map]]

## See also in repo
- `docs/architecture.md`
- `.env.example`
