# Database Model

This note is an operating-level map of database tables and their purpose. Implementation truth lives in `apps/api/prisma/schema.prisma` in the RAi product repo.

## Table map
| Table | Purpose |
|---|---|
| User | Account identity, profile basics, entitlement state, and current credits balance snapshot. |
| Observatory | Top-level user-owned container for domains, systems, and publication activity. |
| Domain | Thematic grouping layer under an observatory for organizing systems and outputs. |
| System | Structured unit of work within a domain, used to generate and publish outputs. |
| Publication | Persisted published artifact and metadata for rendered or AI-assisted output. |
| PublicationUpvote | Join/interaction record for user upvotes on publications. |
| AIGeneration | Trace record of AI generation requests, outputs, cost/usage, and status lifecycle. |
| CreditTransaction | Immutable ledger entry for each credit grant, spend, adjustment, or reversal event. |
| Subscription | Billing and plan lifecycle state linked to a user and payment provider identifiers. |
| ObservatoryVisit | Visit/event tracking record for observatory traffic and engagement snapshots. |

## Operational rule
- Credit balance changes only through `CreditTransaction` plus `User.creditsBalance` mutation in one Prisma transaction.
- Treat `CreditTransaction` as ledger truth and `User.creditsBalance` as fast-read derived state maintained atomically.

## Status notes
- Baseline schema is tracked as applied in [[ISSUE-03]].
- This page remains an operating summary; field-level details belong to implementation sources.

## See also in vault
- [[37_Model_Implementation_Map]]
- [[23_Domain_Model]]
- [[25_Observatory_Model]]
- [[27_Publication_Model]]

## See also in repo
- `docs/architecture.md`
- `apps/api/prisma/schema.prisma`
