# backend (generated)

> Generated from `docs/proposal.md`. Agents: keep up to date with code.

Purpose: define server API contracts, auth, and minimal-resource rules.

Owns: API surface, authN/Z, roles, admin APIs, quotas, minimal-resource posture, enforcement hooks referencing `features`.
Owns not: tier definitions/copy (see `features`), provisioning (see `operations`), runtime lifecycle (see `workspace-runtime`).

Locked:
- Backend owns auth + roles + admin.
- Tier meaning lives in `features`; backend only enforces.
- Minimal backend resources per proposal goal.

Open: endpoint list, role model details, admin actions.
