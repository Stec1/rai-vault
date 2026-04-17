# Publication Model

Publication is formatted proof of work and the core content unit in MVP.
It transforms raw creator output into a consistent, readable research artifact.

## In MVP
- Creator submits raw output.
- RAi AI (GPT-4o) formats submission into a structured presentation.
- Structured publication fields include:
  - Title
  - Summary
  - Key findings
  - Methodology
  - Formatted body
- Publication can optionally associate with a System.
- Publication can optionally associate with a Domain.
- Publication supports tags for topical grouping.
- Community can upvote publications.
- Each publication has a standalone page at `/publication/:id`.
- State model includes draft and published.
- Formatting consumes 1 credit per publication.

## Not in MVP
- Comments/discussion threads.
- Citation manager or formal reference graph.
- Media attachments as a first-class publication feature.

## Key constraints
- Rate limit: maximum 20 publications per user per hour.
- Free tier cap: 5 publications per user per month.
- Publication flow optimizes for structured clarity, not long-form social interaction.

## See also in vault
- [[25_Observatory_Model]]
- [[28_Reputation_Model]]
- [[29_Monetization_Model]]

## See also in repo
- `docs/world-structure.md`
- `docs/mvp-contract.md`
