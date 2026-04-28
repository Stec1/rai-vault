# SI Target ↔ MVP Bridge

This note is the vault-level operating reference for how the current MVP execution leads to the System Intelligence (SI) target architecture.

The authoritative SI documents live in the RAi product repo.

## Status
- SI target accepted as Phase 3+ destination via [[DL-008]].
- Architectural law recorded in [[DL-25]] as a mirror of repo DL-25.
- Active MVP execution unchanged.
- ISSUE-06 is completed in the product repo.
- ISSUE-06 vault closure and Start Page refinement remain separate future passes.
- ISSUE-07 is the next implementation issue.

## What lives where
- Target architecture, canonical full source: `docs/si-target.md` in the RAi product repo.
- MVP-to-SI mapping, canonical full source: `docs/mvp-to-si-bridge.md` in the RAi product repo.
- Repo architectural law: `docs/decision-log.md` DL-25.
- Vault acceptance memory: [[DL-008]].
- Vault mirror of architectural law: [[DL-25]].
- Vault bridge note: this note.
- Supporting exploratory UX narrative: [[SI_UX_Narrative]].

## Operating rules
- This note is a navigation anchor. It does not duplicate repo content.
- The repo remains authoritative for `docs/si-target.md` and `docs/mvp-to-si-bridge.md`.
- When updating the bridge, edit the repo file `docs/mvp-to-si-bridge.md` first, then refresh this note's status block.
- New vault notes must reference repo `docs/si-target.md` rather than redefining SI target concepts.
- No vault note expands MVP scope based on SI content.
- SI references are descriptive unless a dedicated issue explicitly implements them.

## Issue treatment under SI acceptance
- ISSUE-00 through ISSUE-06: completed in the product repo, not modified by SI acceptance.
- ISSUE-06 vault closure: separate future vault pass.
- ISSUE-06 Start Page refinement / domain visual asset work: separate product pass.
- ISSUE-07: next implementation issue.
- ISSUE-07 through ISSUE-20: scope unchanged unless explicitly changed by a future founder decision.
- Post-MVP SI systems require dedicated future issues.

## What must not happen now
- No Commission Layer implementation.
- No Verification Layer implementation.
- No Stripe Connect multi-party payout implementation.
- No A2A endpoint implementation.
- No MCP server implementation.
- No new SI database tables during MVP.
- No reopening completed issues because of SI approval.

## See also in vault
- [[DL-008]]
- [[DL-25]]
- [[SI_UX_Narrative]]
- [[Decision_Index]]
- [[00_Current_State]]
- [[02_MOC_Architecture]]

## See also in repo
- `docs/si-target.md`
- `docs/mvp-to-si-bridge.md`
- `docs/decision-log.md` — DL-25
- `docs/mvp-contract.md`
- `ROADMAP.md`

⸻
