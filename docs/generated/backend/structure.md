# structure (generated)

> Generated from `docs/proposal.md`. Agents: keep up to date with code. Approximate on purpose — doc phase cannot be impl-complete.

Purpose: sketch the axum service layout.

Owns: route families, auth/session plumbing, adapters, byte-forwarding.
Owns not: API contracts (see `backend`), runtime lifecycle (see `workspace-runtime`), trait details (see `devops/tech-stack`).

Locked:
- Route module per endpoint family: workspaces, open/launch, account, admin, health, billing/usage.
- Auth/session plumbing centralized (password check, JWT mint, cookie set, Origin checks, revocation).
- Adapters implement Volumes, Objects, Rdb traits; byte-forwarding to containers in one place.

Open: module/file detail at scaffold.
