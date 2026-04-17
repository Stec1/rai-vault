# Monetization Model

MVP monetization combines credit packs and a Pro subscription, with Stripe as the payment backbone.
Until launch, billing flows run in test mode while preserving production-grade transaction rules.

## In MVP
- Credit packages:
  - Starter: 50 credits for $5
  - Growth: 200 credits for $15
  - Pro Pack: 500 credits for $30
- Pro subscription is $19/month.
- Free tier includes:
  - 5 publications/month
  - 3 systems
  - Basic analytics
  - 10 starting credits
- Billing stack uses Stripe Checkout, Billing, and Customer Portal.

## Credit sinks
- Publication formatting: 1 credit.
- Visual Signature generation: 2 credits.
- Rollback action: 1 credit.

## Not in MVP
- Usage-based metered pricing.
- Enterprise tier packaging.
- Team plans.

## Key constraints
- Credit balance changes only through `CreditTransaction` + `User.creditsBalance` in one Prisma transaction.
- Never mutate credit ledger and balance separately.
- Credit rules must remain deterministic and auditable during MVP.

## See also in vault
- [[25_Observatory_Model]]
- [[27_Publication_Model]]
- [[32_Database_Model]]

## See also in repo
- `docs/mvp-contract.md`
- `docs/architecture.md`
