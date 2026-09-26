# features (generated, non-tech)

> Generated from `docs/proposal.md`. Agents: enforce, do not redefine tiers here.

Purpose: define normal vs premium capability matrix in product terms.

Owns: tier names, capability matrix (storage, shell, extensions, server use, limits).
Owns not: auth mechanics, roles implementation, admin APIs (see `backend`).

Locked:
- Separate non-tech doc; capability-matrix scope.
- Premium: a whole dev-server container to mess with (not a single project): files on server (container filesystem, no S3 backup for now), native shell/terminal, admin-configurable per-workspace quota, full extension ecosystem with no allowlist. Normal: no workspace or container; public repos live only in browser memory, plain Monaco editor with tokenization only, client-side git pull only, no shell.
- Billing is metered on workspace hours and stored GB-hours; usage is recorded, payment comes later.
- The container is the only security boundary; there is no extension restriction to enforce.

Open: upgrade flow (out of scope for now).
