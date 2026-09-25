# tech-stack (generated)

> Generated from `docs/proposal.md`. Agents: keep up to date with code. Humans: principles + candidates only, no versions locked yet.

Purpose: record choices of languages, frameworks, container/k8s approach, S3-first services, and the thin self-defined portability wrapper (dapr-like).

Owns: principles, candidate list with decision criteria, wrapper interfaces, S3-first set + swap strategy.
Owns not: flows (see `architecture`), API shapes (see `backend`), provisioning steps (see `operations`).

Locked:
- Principles + candidates mode (no version pins yet).
- Wrapper lives here, not in deployment.
- S3-first, switchable via thin self-defined interfaces.
- Containers, k8s candidate.

Open: final language/framework picks, wrapper interface shapes.
