# Model Implementation Map

This file bridges product models in `20_Product` with their technical implementation across architecture notes in `30_Architecture` and execution issues in `40_Execution`.

## Mapping table

| Product Model | Core Fields | Implemented In (issue) | Architecture Note | Status |
| --- | --- | --- | --- | --- |
| Domain ([[23_Domain_Model]]) | taxonomy, canonical IDs, relationships | [[ISSUE-03]] | [[32_Database_Model]] | Baseline implemented |
| Observatory ([[25_Observatory_Model]]) | observatory metadata, ownership, lifecycle state | [[ISSUE-03]] | [[32_Database_Model]] | Baseline implemented |
| System ([[26_System_Model]]) | system profile, capabilities, integration hooks | [[ISSUE-03]] | [[32_Database_Model]] | Baseline implemented |
| Publication ([[27_Publication_Model]]) | publication metadata, versioning, status | [[ISSUE-03]] | [[32_Database_Model]] | Baseline implemented |
| Reputation ([[28_Reputation_Model]]) | scoring dimensions, evidence links, confidence | Pending | Pending | Pending |
| Onboarding ([[24_Onboarding_Model]]) | onboarding stage, completion flags, user context, auth route redirect behavior via `/api/me` | [[ISSUE-07]] | [[38_SI_Target_Bridge]] (target remains post-MVP) | Baseline implemented for auth entry UX |
| UI System ([[2A_UI_System]]) | semantic tokens, global styles baseline, typography baseline, responsive Start Page composition (TopBar/Hero/How it Works/Domain showcase/CTA/Footer), mobile typography-first behavior, About/Auth editorial card UI, legal placeholders (`/privacy`, `/terms`) | [[ISSUE-06]], [[ISSUE-07]] | [[38_SI_Target_Bridge]] (target remains post-MVP) | Baseline implemented through Start + About/Auth surfaces |

## How to update

- Update this table whenever a product model is implemented at baseline in execution.
- Update this table whenever a product model is extended with new technical fields or integrations.
- Update this table whenever a product model is refactored; always link the implementing issue and keep status aligned with Current_State.

## Relation

See [[01_MOC_Product]] for model intent, [[02_MOC_Architecture]] for implementation references, and [[03_MOC_Execution]] for issue-level delivery.


## ISSUE-07 implementation notes

- Public About route (`/about`) is implemented with MVP-editorial scope (RAi, Domains, Observatories, Publications, Reputation).
- Auth entry routes (`/login`, `/signup`) are implemented with Better Auth email/password UI.
- Google OAuth remains deferred to ISSUE-04 Phase 2; password reset/email verification screens remain out of scope.
- SI target architecture position is unchanged: accepted as post-MVP target only.
