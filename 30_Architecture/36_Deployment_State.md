# Deployment State

## Production topology (2026-05-15)
- Canonical production frontend: Vercel `rai-web` at `https://rai-web-one.vercel.app`.
- Canonical production API runtime: Railway `@rai/api` at `https://raiapi-production.up.railway.app`.
- Railway project: `gracious-blessing`.
- Railway services: `@rai/api`, `@rai/web`, PostgreSQL, Redis.
- Railway `@rai/web` exists but is not the canonical production frontend.

## Runtime/env alignment (`@rai/api`)
- `WEB_URL=https://rai-web-one.vercel.app`
- `DATABASE_URL=${{ Postgres.DATABASE_URL }}`
- `REDIS_URL=${{ Redis.REDIS_URL }}`
- `BETTER_AUTH_SECRET` present
- `BETTER_AUTH_URL` present

## Operational validation
- Same-origin proxy path active: browser `→ /api/...` on Vercel frontend → Railway API target via `API_PROXY_ORIGIN`.
- `/api/health` returns 200 through proxy.
- `/api/v1/domains` returns 7 domains through proxy.
- Signup/login and `/api/me` session checks are stable through proxy path.

## Data state notes
- Production Postgres migration path executed through Railway CLI with `DATABASE_PUBLIC_URL`.
- Seeded production baseline verified:
  - 7 domains
  - 3 test users
  - 3 test observatories
