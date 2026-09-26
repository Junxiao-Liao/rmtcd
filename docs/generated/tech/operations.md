# operations (generated)

> Generated from `docs/proposal.md`. Agents: keep up to date with code.

Purpose: define how the system runs, deploys, and stays safe and cheap.

Owns: EC2 provisioning, k3s deploy, wildcard DNS/TLS + gateway routing, ops, cost-minimal stance, migration path, threat model + guarantees (hybrid security; enforcement lives in owning docs).
Owns not: wrapper interfaces (see `tech-stack`), API logic (see `backend`), per-container lifecycle (see `workspace-runtime`).

Locked:
- Start: single EC2 + k3s; keep path open to EC2 fleet + managed k8s.
- Workspace-subdomain routing; containers private behind authenticated gateway.
- Real security boundary is container/host isolation, not the extension allowlist: non-root, no priv-esc, dropped caps, seccomp, no host namespaces or runtime socket, scoped mounts (Restricted model), network policies (no cross-workspace, no control-plane/RDS/IMDS from tenants), resource limits against host crash/DoS, disabled port forwarding unless separately designed.
- Minimal resources per proposal goal.

Open: provisioning steps, monitoring, storage-driver/placement for fleet move, measured capacity (idle/index/build/concurrent).
