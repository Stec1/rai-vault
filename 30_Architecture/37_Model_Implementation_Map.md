# Model Implementation Map

This file bridges product models in `20_Product` with their technical implementation across architecture notes in `30_Architecture` and execution issues in `40_Execution`.

## Mapping table

| Product Model | Core Fields | Implemented In (issue) | Architecture Note | Status |
| --- | --- | --- | --- | --- |
| Domain ([[23_Domain_Model]]) | taxonomy, canonical IDs, relationships, topology discovery nodes | [[ISSUE-03]], [[ISSUE-08]], [[ISSUE-08R]] | [[32_Database_Model]], [[33_API_Surface]] | Implemented; seeded and production-validated (7 domains) |
| Observatory ([[25_Observatory_Model]]) | observatory metadata, ownership, lifecycle state | [[ISSUE-03]], [[ISSUE-05]] | [[32_Database_Model]], [[33_API_Surface]] | Baseline identity model implemented; create/dashboard and graph-node expansion remain early/placeholder |
| System ([[26_System_Model]]) | system profile, capabilities, integration hooks | Pending | [[32_Database_Model]] | Not implemented |
| Publication ([[27_Publication_Model]]) | publication metadata, versioning, status | Pending | [[32_Database_Model]] | Not implemented |
| Reputation ([[28_Reputation_Model]]) | scoring dimensions, evidence links, confidence | Pending | Pending | Not implemented |
| Onboarding ([[24_Onboarding_Model]]) | onboarding stage, completion flags, user context, auth route redirect behavior via `/api/me` and `/explore` | [[ISSUE-07]], [[ISSUE-08R]] | [[38_SI_Target_Bridge]] (target remains post-MVP) | Baseline routing/entry UX implemented |
| UI System ([[2A_UI_System]]) | semantic tokens, global styles baseline, Start Page baseline, Explore SVG topology, canonical TopBar roles, PNG cleanup | [[ISSUE-06]], [[ISSUE-07]], [[ISSUE-08R]] | [[38_SI_Target_Bridge]] (target remains post-MVP) | MVP baseline implemented through Start/About/Auth/Explore topology surfaces |

## How to update

- Update this table whenever a product model is implemented at baseline in execution.
- Update this table whenever a product model is extended with new technical fields or integrations.
- Update this table whenever a product model is refactored; always link the implementing issue and keep status aligned with Current_State.

## Relation

See [[01_MOC_Product]] for model intent, [[02_MOC_Architecture]] for implementation references, and [[03_MOC_Execution]] for issue-level delivery.

## Post-ISSUE-08R notes

- `/explore` is currently SVG-based MVP topology, not Three.js/R3F-mandated implementation.
- Observatory nodes on explore graph are not recorded as implemented.
- SI target architecture position remains unchanged: accepted as post-MVP target only.
