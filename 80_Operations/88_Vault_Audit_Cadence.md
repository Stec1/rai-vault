# Vault Audit Cadence

This file defines the regular audit rhythm for rai-vault so graph integrity, link coherence, and memory accuracy do not drift.

## Audit types and frequency

| Audit type | Frequency | Output location | Trigger |
|---|---|---|---|
| Link audit (automated scan) | Weekly | `60_Audits/YYYY-MM-DD_Vault_Link_Audit.md` | Sunday, or before starting a new issue |
| MOC coherence check | Weekly | Same audit file, section | Same cadence as link audit |
| Decision mirror sync | Per merge | Inline in merge report | After any merge that touches 70_Decisions or docs/decision-log.md |
| Phase retrospective | End of phase | `60_Audits/YYYY-MM-DD_Phase_Retro.md` via [[Template_Phase_Retrospective]] | After last issue of a phase is merged |
| Full vault audit | Monthly | `60_Audits/YYYY-MM-DD_Full_Vault_Audit.md` | First week of month |

## Weekly link audit checklist

- Run automated link scan; record unresolved wiki-links and orphan notes
- Verify [[00_MOC_RAi]] lists every active note in Core Areas without duplicates
- Confirm no note in `20_Product/` or `30_Architecture/` is an orphan
- Confirm every DL note in [[Decision_Index]] has at least one inbound link
- Log findings as new note in `60_Audits/` with explicit recommendations

## Entry rule

- Audit notes always land in `60_Audits/`, never in operations or execution folders
- Each audit note must link to [[00_Current_State]] and at least one follow-up action if gaps are found

## Relation

- Governed by [[85_Update_Protocol]] as a recurring event type
- Audit findings feed into [[01_Next_Action]] when action is required

## See also
- [[86_Agent_Entry_Protocol]]
- [[87_Graph_Conventions]]
