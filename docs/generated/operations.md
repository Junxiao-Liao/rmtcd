# operations (generated)

> Generated from `docs/proposal.md`. Agents: keep up to date with code.

Purpose: define how the system runs, deploys, and stays safe and cheap.

Owns: EC2 provisioning, k3s deploy, ops, cost-minimal stance, migration path, threat model + guarantees (hybrid security; enforcement lives in owning docs).
Owns not: wrapper interfaces (see `tech-stack`), API logic (see `backend`), per-container lifecycle (see `workspace-runtime`).

Locked:
- Start: single EC2 + k3s; keep path open to EC2 fleet + managed k8s.
- Minimal resources per proposal goal.
- Hybrid security: guarantees here, enforcement local.

Open: provisioning steps, monitoring, migration triggers.
