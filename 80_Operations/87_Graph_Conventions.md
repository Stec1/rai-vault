# Graph Conventions

This document defines the graph group logic for rai-vault so the founder and any agent can quickly understand and maintain the intended visual layout in [[README]] and [[00_MOC_RAi]].

## Group tiers

| Tier | Group | Path pattern | Role |
|---|---|---|---|
| Tier 0 | Operating Core | `00_MOC`, `README`, `00_Current_State`, `01_Next_Action` | Daily entry points |
| Tier 1 | Protocol | `80_Operations` | Rules and checkpoints |
| Tier 2 | Decisions | `70_Decisions` | Executive memory |
| Tier 3 | Execution | `40_Execution` | Live work |
| Tier 4 | Ontology | `10_Foundation`, `20_Product`, `30_Architecture` | Stable context |
| Tier 5 | Toolkit | `50_Prompts` | Reusable prompts |
| Tier 6 | Audits | `60_Audits` | Verification trail |
| Tier 7 | Notes | `100_Notes` | Exploratory zone |
| Tier 8 | Archive | `90_Archive` | Historical |

## How groups are wired

- Graph grouping is defined centrally in `.obsidian/graph.json` under `colorGroups`, with one query per tier.
- The query filters use `path:` and `file:` selectors so placement and known hub filenames determine node grouping automatically.
- `showOrphans` remains enabled to surface isolated notes for cleanup and routing.
- `.obsidian/snippets/rai-vault-graph.css` applies visual emphasis to the Tier-0 hub labels only, while structure is governed by graph settings.

## Adding new notes

- Create each note in the correct folder first; folder placement determines graph grouping.
- Existing `colorGroups` queries auto-assign the note to its group if the path matches.
- No manual color assignment is needed unless the founder intentionally retunes groups in Obsidian UI.

## Hub nodes

- [[README]]
- [[00_MOC_RAi]]
- [[00_Current_State]]
- [[01_Next_Action]]
- [[Decision_Index]]

## Color assignment

Exact colors are founder-selected. The current `.obsidian/graph.json` values are placeholder RGB choices that can be adjusted later in Obsidian UI without changing this tier structure.
