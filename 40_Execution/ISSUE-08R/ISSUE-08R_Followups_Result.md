# ISSUE-08R Follow-ups Result

## Final status
**ISSUE-08R.1 / ISSUE-08R.2 / ISSUE-08R.3 / ISSUE-08R.4 are completed as follow-up stabilization and cleanup chain.**

## ISSUE-08R.1 — Routing + Explore Chrome Correction
- `/` Start Page renders for all visitors; authenticated users are not forced away from Start Page.
- TopBar became auth-aware in first follow-up iteration:
  - guest → Log in / Get Started
  - authNoObservatory → Explore / Create Observatory
  - authWithObservatory → Explore / Dashboard
- This interim TopBar arrangement was later superseded by canonical DL-28 in ISSUE-08R.4.

## ISSUE-08R.2 — Topology Canvas Pan/Zoom Hardening
- Fixed trackpad/two-finger scroll-jump behavior on `/explore`.
- Topology interaction upgraded to controlled surface:
  - pointer-centered zoom,
  - scale-aware pan,
  - native non-passive wheel listener,
  - document scroll lock while interacting inside explore topology.
- Surface prepared for future observatory-node expansion without declaring that expansion completed.

## ISSUE-08R.3 — PNG Domain Asset Cleanup
- Founder decision removed PNG domain objects from MVP visual system.
- `apps/web/public/domain-objects/**` assets removed in product repo implementation stream.
- Start Page removed PNG domain showcase and decorative RA PNG usage in hero context.
- Canonical domain visualization became SVG topology on `/explore`.
- Domain visuals outside `/explore` were deferred.
- DL-27 added.

## ISSUE-08R.4 — Canonical TopBar + Routing Cleanup (Variant B)
- RAi logo now routes to `/`.
- TopBar is navigation, not duplicate primary CTA surface.
- `Create Observatory` removed from TopBar.
- Primary CTA `Create Observatory` remains in Explore info panel for authNoObservatory users and routes to `/create`.
- Canonical TopBar states:
  - guest → About / Log in / Get Started
  - authNoObservatory → Explore / About / Sign out
  - authWithObservatory → Explore / Dashboard / Sign out
- Simple Sign out was added.
- DL-28 added.
- Explicit non-scope for ISSUE-08R.4 remained unchanged:
  - no apps/api edits,
  - no Prisma/Redis schema changes,
  - no next.config changes,
  - no post-auth redirect contract rewrite beyond established direction,
  - no explore topology rewrite,
  - no pan/zoom rollback,
  - no PNG-cleanup rollback,
  - no cookie/session config rewrite,
  - no package manifest/lockfile changes.
