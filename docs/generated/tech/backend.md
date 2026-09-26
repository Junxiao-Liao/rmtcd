# backend (generated)

> Generated from `docs/proposal.md`. Agents: keep up to date with code.

Purpose: define server API contracts, auth, and minimal-resource rules.

Owns: API surface, authN/Z, fixed access levels, admin APIs, quotas, JWT issuance, minimal-resource posture, enforcement hooks referencing `features`.
Owns not: tier definitions/copy (see `features`), provisioning (see `operations`), runtime lifecycle (see `workspace-runtime`).

Locked:
- Rust backend; backend owns auth + roles + admin. Login is username + password, passwords hashed in Postgres. Signup is invite-only.
- No user-facing Exec shell endpoint; shell flows through the Rust-forwarded native terminal.
- Workspace routing by ID (owner/policy/entitlement/generation -> current private service); JWT launch + session pair (1-minute launch, 12-hour session, audience-bound; minimal claims: subject, workspace audience, tier, generation, expiry), host-only cookies, per-endpoint Origin checks, revocation closes live sockets.
- API shape is REST for CRUD and admin, plus WebSocket only where streaming needs it.
- The Rust backend itself forwards browser-to-editor bytes after auth; no separate proxy box.
- First endpoint families: workspaces, open/launch, account, admin, health, plus billing and usage. Billing is metered on workspace hours and stored GB-hours; usage is recorded, payment comes later. Quotas change through admin API + pages.
- Admin pages hold users, workspaces, quotas, and usage; nothing else day one.
- Logout kills app and workspace sessions plus live sockets.
- Authorization is fixed levels (none, viewer, editor, admin), checked on every request: viewer reads, editor changes, admin manages access and quotas. Normal users have no project entity (frontend memory only); premium scope is the whole workspace container, not a single project.
- Minimal backend resources per proposal goal.

Open: endpoint list, access-level details.
