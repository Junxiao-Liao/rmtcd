# tech-stack (generated)

> Generated from `docs/proposal.md`. Agents: keep up to date with code. Humans: principles + candidates only.

Purpose: record choices of languages, frameworks, container/k8s approach, S3-first services, and the thin self-defined portability wrapper (dapr-like).

Owns: principles, candidates with decision criteria, wrapper interfaces, code-server choice, S3-first set + swap strategy.
Owns not: flows (see `architecture`), API shapes (see `backend`), provisioning steps (see `operations`).

Locked:
- Backend: Rust (leanest pick). Frontend shell: Angular; premium IDE is code-server web (not custom Monaco).
- Wrapper is in-process facade (not sidecar): Platform.Storage + Platform.Rdb from the start; Platform.Exec dropped as user shell with backend-shell removal (revisit only if non-shell app need arises).
- RDB: Postgres on RDS first; optimize for Postgres-to-Postgres portability.
- Containers on k3s; code-server per premium workspace.

Open: crate/framework shortlist, wrapper interface shapes, extension allowlist contents.
