# ISSUE-08 Recovery Notes

## Production Auth / API Runtime Recovery

### Canonical production endpoints
- Web frontend: `https://rai-web-one.vercel.app` (Vercel service: `rai-web`).
- API origin: `https://raiapi-production.up.railway.app` (Railway API runtime).

### Runtime topology
- Railway project: `gracious-blessing`.
- Runtime services in project: `@rai/api`, `@rai/web`, PostgreSQL, Redis.
- Canonical production frontend is Vercel `rai-web`, not Railway `@rai/web`.

### Railway `@rai/api` environment corrections
- `WEB_URL=https://rai-web-one.vercel.app`
- `DATABASE_URL=${{ Postgres.DATABASE_URL }}`
- `REDIS_URL=${{ Redis.REDIS_URL }}`
- `BETTER_AUTH_SECRET` present
- `BETTER_AUTH_URL` present

### Data/runtime recovery actions
- Production Postgres migrations executed via Railway CLI using `DATABASE_PUBLIC_URL`.
- Production seed confirmation recorded:
  - 7 domains
  - 3 test users
  - 3 test observatories

### Production validation outcomes
- `/api/health` returns 200 through Vercel same-origin proxy path.
- `/api/v1/domains` returns 7 domains through Vercel same-origin proxy path.
- Signup/login through Vercel `/api/...` path creates valid sessions.
- `/api/me` returns 200 after auth via same-origin proxy flow.

### Same-origin proxy correction
- Browser path: `/api/...` on Vercel origin.
- Vercel proxy target set by:
  - `API_PROXY_ORIGIN=https://raiapi-production.up.railway.app`
- Result: cross-origin cookie/session failure mode removed by same-origin proxy strategy.

### Hardening and bug fixes
- Redis literal-reference configuration issue was corrected.
- Rate-limit handling was hardened to avoid leaking raw Redis errors to clients.
