# backend (generated)

> Generated from `docs/proposal.md`. Agents: keep up to date with code.

Purpose: define server API contracts, auth, and minimal-resource rules.

Owns: API surface, authN/Z, roles + project grants, admin APIs, quotas, launch-code issuance, minimal-resource posture, enforcement hooks referencing `features`.
Owns not: tier definitions/copy (see `features`), provisioning (see `operations`), runtime lifecycle (see `workspace-runtime`).

Locked:
- Rust backend; backend owns auth + roles + admin.
- No user-facing Exec shell endpoint; shell flows through the gateway-proxied native terminal.
- Workspace routing by ID (owner/policy/entitlement/generation -> current private service); single-use launch codes, host-only cookies, per-endpoint Origin checks, revocation closes live sockets.
- Minimal backend resources per proposal goal.

Open: endpoint list, role/grant details, launch-code TTL and session bounds.
