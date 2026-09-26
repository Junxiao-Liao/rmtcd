# operations (generated)

> Generated from `docs/proposal.md`. Agents: keep up to date with code.

Purpose: define how the system runs, deploys, and stays safe and cheap.

Owns: EC2 provisioning, k3s deploy, wildcard DNS/TLS + subdomain routing, ops, cost-minimal stance, migration path, threat model + guarantees (hybrid security; enforcement lives in owning docs).
Owns not: wrapper interfaces (see `tech-stack`), API logic (see `backend`), per-container lifecycle (see `workspace-runtime`).

Locked:
- Dev runs fully local with no cloud account. Deploy target is a single EC2 + k3s box (Cloudflare free tier in front while personal-scale), provisioned by the full-host-setup script from the first deploy; fleet path stays open. Deployability comes from one artifact set (images + manifests + setup script).
- Workspace-subdomain routing with opaque IDs (no owner info in hostnames); containers private behind the Rust backend.
- Real security boundary is container/host isolation: non-root, no priv-esc, dropped caps, seccomp, no host namespaces or runtime socket, scoped mounts (Restricted model), network policies (no cross-workspace, no control-plane/RDS/IMDS from tenants), resource limits against host crash/DoS, disabled port forwarding unless separately designed.
- Fleet disk placement is decided at the fleet move, not now.
- Observability starts with persisted logs plus health endpoints; metrics and alerting later.
- Minimal resources per proposal goal.

Open: provisioning script contents at build; fleet placement deferred to the move.
