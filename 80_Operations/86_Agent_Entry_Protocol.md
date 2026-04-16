# Agent Entry Protocol

This file defines the strict reading order any agent must follow when entering
rai-vault for a new session so actions begin from current operating context,
not from assumptions.

## Reading order

1. [[README]] (30-second orientation)
2. [[00_MOC_RAi]] (navigation map)
3. [[00_Current_State]] (what is now)
4. [[01_Next_Action]] (what is next)
5. Active [[40_Execution/ISSUE-XX]] folder — all files in it
6. [[80_Working_Model]], [[82_Handoff_Rules]], [[83_Agent_Usage_Instructions]]
7. [[Decision_Index]] — latest 3–5 decisions

## Before proposing any action

Confirm all items below before acting:

- Active issue is explicit (or explicit no-active-issue state) in [[00_Current_State]].
- Current readiness and priority are explicit in [[01_Next_Action]].
- No unresolved blocker, dependency, or stop condition is present in [[00_Current_State]].
- The intended action aligns with constraints from [[80_Working_Model]] and [[82_Handoff_Rules]].
- The intended action does not conflict with recent entries in [[Decision_Index]].

## When to stop and ask founder

Do not proceed autonomously when any of the following is true:

- [[00_Current_State]] is stale, missing, or inconsistent with active issue artifacts.
- Multiple authoritative records (for example in [[Decision_Index]] and issue notes) contradict each other.
- A blocker is unresolved in [[00_Current_State]] and no explicit bypass decision exists.

## Entry completion check

Only proceed when all checks are true:

- You can name the active issue and its exact status.
- You can restate the next concrete action from [[01_Next_Action]].
- You can state whether blockers exist in [[00_Current_State]].
- You can cite at least one relevant recent decision from [[Decision_Index]].

## Execution stance

After the reading order is complete:

- Use [[01_Next_Action]] as the default execution anchor.
- Treat [[00_Current_State]] as the source of truth for status and blockers.
- Record any newly discovered mismatch before proposing substantial new work.
- Prefer continuity with active issue artifacts in [[40_Execution/ISSUE-XX]].

## Escalation hygiene

When escalation is required:

- State exactly which source is inconsistent (for example [[00_Current_State]] vs issue log).
- Propose one minimal clarification question to restore forward motion.
- Do not create new planning branches until founder confirms direction.

## Scope rule

- Follow this protocol for every new session, including handoff-only sessions.
- If the active issue changes mid-session, restart the reading order from [[00_Current_State]].
