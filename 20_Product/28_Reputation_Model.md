# Reputation Model

Reputation is a numeric score accumulated from activity and community evaluation, not a star-rating system.
In MVP it is an operational trust signal attached to Observatory-level consistency and validated output.

## In MVP
- Reputation is computed from fixed positive actions.
- Formula inputs and base values:
  - Complete Observatory profile: +10
  - Register System: +5
  - Publish research: +5
  - Publication reaches 10+ upvotes: +10
  - Publication reaches 50+ upvotes: +25
  - Consistent publishing (4+ per month): +15 streak bonus
- Score is shown on the Observatory page.
- Score and contribution breakdown are shown in Control Panel.
- Reputation influences sort order in Explore Observatories.
- Model follows the directional decision DL-22 in `docs/decision-log.md` against star-style ratings.

## Not in MVP
- Star ratings.
- Review-average style scoring.
- Negative reputation deductions.

## Formula
- Reputation = sum of eligible positive events + consistency bonus.
- Threshold bonuses are additive on top of base publication actions.
- Time-based streak bonus is evaluated on monthly consistency windows.

## Key constraints
- Formula is a first approximation for MVP.
- Weighting is expected to be tuned after soft launch as a tracked backlog adjustment.

## See also in vault
- [[25_Observatory_Model]]
- [[27_Publication_Model]]
- [[Decision_Index]]

## See also in repo
- `docs/decision-log.md` (DL-22)
- `docs/mvp-contract.md`
