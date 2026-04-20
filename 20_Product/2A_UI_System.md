---
type: product-ontology
status: active
owner: founder
last_reviewed: 2026-04-20
---

# UI System

## Purpose
Operating contract for the RAi visual language at product level. Names semantic roles, rules, and a review gate that every UI-related issue must satisfy before merge. Exact token values (hex, px, ms, font urls) live in the product repo at `docs/visual-reference.md` — this note references roles, not values.

## Visual Direction
Premium dark editorial. Dark mode only in MVP. Layering communicated through typography hierarchy and surface elevation, not decoration. Warm white-gold reserved for RA; one cold blue UI accent; Domain colours used only for identification of Observatory/Domain/node, never as UI chrome.

## Interface Character
- Instrumental, not decorative
- Editorial, not flat
- Quiet, not loud
- Data-first, content-first
- Dark-only in MVP
- No marketing tone in UI copy

## Design Tokens — Semantic Roles
Values are defined in `docs/visual-reference.md`. This note fixes roles.

| Token role | Intended use |
|---|---|
| `surface.base` | Start page and global background |
| `surface.canvas` | Intelligence topology area |
| `surface.panel` | UI panels and chrome |
| `surface.elevated` | Editorial and publication cards |
| `text.primary` | Body and heading text |
| `text.secondary` | Metadata, timestamps, muted labels |
| `accent.cold` | Single UI accent for interactive state |
| `accent.warm` | Reserved for RA hub only |
| `border.hairline` | Default border across UI |
| `signal.success` | Positive system state |
| `signal.danger` | Errors and destructive actions |
| `domain.<slug>` | Identification of a Domain or Observatory association only |

Rule: at most one UI accent colour is active in UI chrome at a time. Domain colours never act as UI chrome.

## Typography Logic
- Display / Hero: Space Grotesk, weights 300 or 700 only.
- Body / UI: Inter or system sans-serif fallback.
- Mono: JetBrains Mono, reserved for Observatory addresses and technical content inside publications.
- Size scale: only the tokens defined in `docs/visual-reference.md` are allowed.
- Maximum 3 font sizes per screen.
- Uppercase labels use increased letter-spacing as defined in the visual reference.

## Spacing Rhythm
- Base unit: spacing base token from `docs/visual-reference.md`.
- Allowed steps only: named spacing tokens from the visual reference scale.
- Minimum gap between adjacent elements: minimum separation token from the visual reference.

## Layout Principles
- 12-column grid on desktop, 4-column on mobile.
- Editorial reading measure: standard editorial reading-width token range.
- Hero max-width: bounded by the visual-reference hero container token.
- Section vertical gap: large on desktop, reduced but roomy on mobile, per visual-reference spacing tokens.
- At most 5 interactive elements visible in a single section of the screen.

## Surface Rules
- Two surface modes: editorial (solid, elevated) and floating (glass over canvas).
- Maximum 2 levels of blur depth per screen.
- Start page uses lighter glass; dashboard and creation flow use heavier surfaces.
- Publication cards are always solid, never glass.
- Depth is communicated through border, opacity, and spacing — not shadows.

## Component Behavior Contract
- Button: solid or ghost only; no gradient; no shadow; focus ring uses `accent.cold`.
- Input: `border.hairline`; focus shifts border colour; no glow.
- Card (editorial): solid `surface.elevated`; radius per visual reference; no shadow.
- Card (floating): glass over canvas only; blur within allowed range.
- Tag / Chip: outline only; uppercase micro-label.
- Link: underline on hover; no colour change in body text.

## Motion Principles
- Motion communicates state change only.
- Allowed: short fade, slide-in from edge, scroll-reveal fade-up, ambient RA pulse.
- Forbidden: bounce, elastic, shake, auto-rotating camera, looping animation on idle UI elements.
- Exact durations and curves live in `docs/visual-reference.md`.

## Color Role Model
- One UI accent at a time (`accent.cold`).
- `accent.warm` is reserved for RA hub; never used for general UI.
- Domain colours only tag Observatories, Domain nodes, and Domain association UI.
- `signal.success` and `signal.danger` are muted, never harsh.

## Anti-Patterns (hard ban)
- Generic SaaS landing patterns: testimonials band, pricing tiers, feature icons grid.
- Cosmic, space, or metaverse imagery and copy.
- Neon primary colours.
- Shadows as the primary depth tool.
- Marketing hyperbole in UI copy.
- Light mode in MVP.
- More than one UI accent colour active simultaneously.
- Decorative illustrations, gradient orbs, animated background blobs.
- More than 5 interactive elements in a single section.

## Review Gate Checklist
Every UI-related issue must satisfy this checklist before merge.

- [ ] All colours used map to a semantic token role defined above.
- [ ] No font size outside the scale in `docs/visual-reference.md`.
- [ ] No spacing value outside the allowed steps.
- [ ] No more than 5 interactive elements per section.
- [ ] No more than one UI accent colour active at once.
- [ ] No shadows used as primary depth.
- [ ] Motion limited to allowed set.
- [ ] No anti-pattern listed above is present.
- [ ] Mobile layout verified on narrow viewport.
- [ ] Screen behaviour is consistent with `docs/visual-reference.md`.

## Change Policy
- Any change to this note requires a corresponding decision note in `70_Decisions/` and an update entry referenced from `[[Decision_Index]]`.
- `docs/visual-reference.md` remains the implementation truth for exact values.
- Status of UI System coverage is tracked in `[[37_Model_Implementation_Map]]`.

## Relation
- [[01_MOC_Product]]
- [[20_Product_Vision]]
- [[22_Full_Product_Map]]
- [[37_Model_Implementation_Map]]
- [[Decision_Index]]
- Product repo: `docs/visual-reference.md`
