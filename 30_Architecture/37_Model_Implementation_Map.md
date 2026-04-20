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
| Onboarding ([[24_Onboarding_Model]]) | onboarding stage, completion flags, user context | Pending | Pending | Pending |
| UI System ([[2A_UI_System]]) | semantic tokens, layout, motion, surface rules | Pending (ISSUE-06 onward) | Pending | Pending |

## How to update

- Update this table whenever a product model is implemented at baseline in execution.
- Update this table whenever a product model is extended with new technical fields or integrations.
- Update this table whenever a product model is refactored; always link the implementing issue and keep status aligned with Current_State.

## Relation

See [[01_MOC_Product]] for model intent, [[02_MOC_Architecture]] for implementation references, and [[03_MOC_Execution]] for issue-level delivery.
