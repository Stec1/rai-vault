# Observatory Model

Observatory is the core product object: one permanent public research space per user.
It serves as the durable identity layer where systems, publications, and reputation converge.

## In MVP
- One canonical public address per Observatory: `rai.app/@name`.
- Observatory has a permanent unique name.
- `ObservatoryType` values are `individual`, `studio`, or `product` per [[DL-006]].
- Visual Signature is part of Observatory identity.
- Observatory associates with 1-2 Domains.
- Observatory supports public and private modes.
- Systems attach to Observatory as operating entities.
- Publications attach to Observatory as proof-of-work outputs.
- Reputation score accumulates at Observatory level.
- Observatory is the primary unit in Explore and profile-level discovery.

## Not in MVP
- Multi-user/shared Observatories.
- Verification badges.
- Enterable spatial/3D Observatory experiences.

## Key constraints
- Exactly 1 Observatory per user account.
- Observatory name must be globally unique and permanent once set.
- Core identity fields should stay stable to preserve canonical links and trust continuity.

## See also in vault
- [[23_Domain_Model]]
- [[26_System_Model]]
- [[27_Publication_Model]]
- [[28_Reputation_Model]]

## See also in repo
- `docs/world-structure.md`
- `docs/mvp-contract.md`
