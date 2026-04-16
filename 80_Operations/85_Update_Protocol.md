# Update Protocol

This file is the post-action checklist for the vault: after each meaningful event,
update the required records in the same working session so execution memory stays
accurate, navigable, and usable for the next handoff.

## Event → Update matrix

| Event | Files to Update | Links to Create |
|---|---|---|
| Issue completed (merge done) | [[00_Current_State]]; [[01_Next_Action]]; active issue notes in [[00_Current_State]]; merge report artifact from [[Merge_Report_Template]]; [[Decision_Index]] if a decision was made | Link issue → merge report; merge report → issue; decision note ↔ issue when applicable |
| Issue started (moved from planned to in_progress) | [[00_Current_State]]; [[01_Next_Action]]; active issue folder in [[00_Current_State]] | Link current state → active issue; active issue → next action |
| Decision made | New decision note in [[Decision_Index]] using [[Template_Decision_Record]]; [[Decision_Index]]; [[00_Current_State]] if execution state changed | Decision note ↔ triggering issue; decision note ↔ affected product/architecture docs |
| Audit completed | New entry in [[60_Audits/README|Audits]]; [[00_Current_State]]; [[01_Next_Action]] when follow-up is required | Audit note ↔ issue artifacts; audit note ↔ next action; audit note ↔ decision when relevant |
| Reusable prompt identified | Prompt note in [[04_MOC_Prompts]]; [[04_MOC_Prompts]] if discoverability changed; optional status note in [[00_Current_State]] | Prompt note ↔ source issue/audit; prompt note ↔ workflow docs |
| Architecture change detected | Relevant files in [[02_MOC_Architecture]]; [[00_Current_State]]; [[Decision_Index]] for policy-level changes | Architecture note ↔ triggering issue/audit; architecture note ↔ governing decision |
| Idea promoted from 100_Notes to Decisions | Source idea in [[100_Notes/README|Exploratory Notes]]; new decision note in [[Decision_Index]]; [[Decision_Index]]; [[00_Current_State]] if direction changed | New decision note ↔ original idea note; decision note ↔ execution artifacts |

## Hard rules

- [[00_Current_State]] is updated within the same session as the event.
- No merge is closed without a merge report artifact linked from execution memory.
- No decision lives only in chat; every decision is documented and indexed in [[Decision_Index]].
- [[01_Next_Action]] always reflects the top executable step after a status-changing event.
- Any new artifact must include at least one inbound and one outbound vault link.
- If two records disagree, resolve inconsistency immediately before closing the session.

## Link quality standard

For each updated artifact:

- Add links to at least one index or navigation page (for example [[Decision_Index]]).
- Add links to at least one execution record (for example an issue note in [[40_Execution]]).
- Ensure link labels are explicit enough to recover context without reopening chat logs.

## Session close micro-check

Before ending work, quickly verify:

- The latest event appears in [[00_Current_State]].
- The next operator can continue directly from [[01_Next_Action]].
- New artifacts are discoverable via at least one index/MOC.
- Any decision-level change is visible in [[Decision_Index]].

## Escalation triggers

Stop and escalate to founder if:

- Event classification is unclear (for example change could be both audit and decision).
- A merge exists but no report artifact can be located or reconstructed.
- Current status in [[00_Current_State]] conflicts with issue-level facts.

## Relation to Vault Handbook

For the long-form rationale and operating details, see [[84_Vault_Handbook]].

## Minimum artifacts per event

- One status artifact update (usually [[00_Current_State]]).
- One execution continuity artifact update (usually [[01_Next_Action]]).
- One traceability link to index, issue, audit, or decision.
