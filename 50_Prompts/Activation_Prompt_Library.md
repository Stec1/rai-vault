# Activation Prompt Library

Reusable commands for the RAi Project Memory Architect agent.
Copy-paste ready. Each command activates a specific operating mode.

---

## 1. Full audit
**When:** Before starting a new phase or after an extended pause.
**Prompt:** "Run a full audit of RAi repo and rai-vault. Give SECTION 1–5 format."
**Expected output:** Structured audit with findings, gaps, recommendations.

## 2. Readiness check
**When:** Before starting work on a specific issue.
**Prompt:** "Readiness check for ISSUE-XX. Verify prerequisites, risks, go/no-go."
**Expected output:** Readiness verdict + risk list + recommendation.

## 3. Code prompt
**When:** A clean prompt is needed for handoff to Code/Codex.
**Prompt:** "Prepare Code prompt for ISSUE-XX. English, strict scope, acceptance criteria."
**Expected output:** Ready-to-paste prompt for Code agent.

## 4. Merge report
**When:** After completing a merge.
**Prompt:** "Merge report for ISSUE-XX. What changed, what to record in vault."
**Expected output:** Filled merge report template.

## 5. Vault fill plan
**When:** Vault needs updates or expansion.
**Prompt:** "What is missing in the vault right now? Give a phased fill plan."
**Expected output:** Gap analysis + phased fill plan.

## 6. Decision sync
**When:** After new decisions in repo or chat.
**Prompt:** "Sync Decision_Index with repo decision-log. What is missing from vault?"
**Expected output:** List of missing decisions + proposed DL entries.

## 7. Issue memory pack
**When:** Closing an issue — everything must be captured.
**Prompt:** "Produce issue memory pack for ISSUE-XX: result, lessons, decisions, next."
**Expected output:** Complete issue closure documentation.

## 8. Current state update
**When:** After any meaningful progress.
**Prompt:** "Update Current State and Next Action in vault."
**Expected output:** Updated state snapshot + next action.

## 9. Structure proposal
**When:** Vault needs new sections or reorganization.
**Prompt:** "Propose a structural improvement to the vault. What to add, what to reorganize."
**Expected output:** Structure proposal with rationale.

## 10. Risk scan
**When:** Before an important merge or decision.
**Prompt:** "Risk scan for current project state. What can go wrong?"
**Expected output:** Risk register with severity and mitigation.

## 11. Diff review prep
**When:** Before reviewing a merge request.
**Prompt:** "Prepare review checklist for ISSUE-XX diff."
**Expected output:** Review checklist aligned with acceptance criteria.

## 12. Quick status
**When:** Short overview needed without deep analysis.
**Prompt:** "Quick status: where we are, what is next, what risks exist."
**Expected output:** 3-line verdict: state / next / risks.

## 13. Prompt review
**When:** A Code prompt is ready — validation needed.
**Prompt:** "Review this Code prompt: [paste]. Is it clear, scoped, safe?"
**Expected output:** Verdict + suggested improvements.

## 14. Backlog triage
**When:** Ideas or backlog items have accumulated.
**Prompt:** "Triage backlog: what is relevant, what to defer, what to drop."
**Expected output:** Categorized backlog with recommendations.

## 15. Architecture alignment check
**When:** Suspicion that implementation drifts from architecture contract.
**Prompt:** "Check alignment between implementation and docs/architecture.md."
**Expected output:** Alignment report with deviations.

## 16. Template generation
**When:** A new template is needed in vault.
**Prompt:** "Create a template for [document type]. Vault-ready .md format."
**Expected output:** Ready template file.

## 17. 100_Notes → Decision promotion
**When:** An idea from notes is ready to become a decision.
**Prompt:** "Evaluate idea [name] from 100_Notes. Is it ready for promotion to Decisions?"
**Expected output:** Verdict + migration path if ready.

## 18. Issue planning
**When:** Planning a new issue from scratch.
**Prompt:** "Plan ISSUE-XX: scope, dependencies, risks, acceptance criteria, Code prompt."
**Expected output:** Complete issue planning package.

## 19. Retrospective
**When:** After completing a phase or milestone.
**Prompt:** "Retrospective for phase [X]: what went well, what did not, what to change."
**Expected output:** Structured retrospective.

## 20. Vault health check
**When:** Periodic vault integrity check.
**Prompt:** "Vault health check: what is stale, what is empty, what is inconsistent."
**Expected output:** Health report with action items.
