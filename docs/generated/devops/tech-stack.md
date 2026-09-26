# tech-stack (generated)

> Generated from `docs/proposal.md`. Agents: keep up to date with code.

Purpose: record choices of languages, frameworks, container/k8s approach, S3-first services, and the thin self-defined portability wrapper (dapr-like).

Owns: principles, candidates with decision criteria, wrapper interfaces, code-server choice, S3-first set + swap strategy.
Owns not: flows (see `architecture`), API shapes (see `backend`), provisioning steps (see `operations`).

Locked:
- Backend: Rust on axum (leanest pick). Frontend shell: Angular; premium IDE is code-server web (not custom Monaco), release pinned and upgraded deliberately.
- Wrapper is in-process (not sidecar), one trait per capability: Volumes (create/delete workspace disks; EBS first adapter), Objects (put/get app objects; S3-shaped, unused for now), Rdb (users, workspaces, quotas, usage rows). No Exec trait.
- RDB: smallest Postgres on RDS first with backups on, scale when needed; optimize for Postgres-to-Postgres portability.
- Containers on k3s; code-server per premium workspace.

Open: crate versions, exact trait signatures at scaffold.
