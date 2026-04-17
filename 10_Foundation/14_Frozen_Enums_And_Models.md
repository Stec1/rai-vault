# Frozen Enums and Models

This file tracks currently frozen assumptions used across docs and prompts.

## Frozen Product Model (Current)
- Product identity: premium observatory platform.
- Core entities: Domain, System, Observatory, Publication.
- Execution model: issue-driven with readiness + review artifacts.

## Frozen Enums
- **ObservatoryType:** `individual` | `studio` | `product` (see [[DL-006]])
- **SystemType:** `agent` | `workflow` | `tool` | `service`
- **SystemStatus:** `active` | `demo` | `concept`
- **PublicationStatus:** `draft` | `published`
- **PlanTier:** `free` | `pro`
- **DomainSlug (active):** `nexum` | `keth` | `solum`
- **DomainSlug (coming soon):** `vorda` | `lyren` | `auren` | `draxis`

## Naming Constraints
- Keep observatory/system/publication terminology stable.
- Do not reintroduce metaverse framing.

## Change Policy
Only update frozen models through a recorded decision in [[Decision_Index]].

## See also
- [[12_Terminology_Dictionary]]
- [[32_Database_Model]]
- [[Decision_Index]]
