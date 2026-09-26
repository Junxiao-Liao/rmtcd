# structure (generated)

> Generated from `docs/proposal.md`. Agents: keep up to date with code. Approximate on purpose — doc phase cannot be impl-complete.

Purpose: sketch provisioning and deploy layout.

Owns: setup script shape, k3s manifests, image definition, Cloudflare hooks.
Owns not: runtime behavior (see `operations`), stack choices (see `tech-stack`).

Locked:
- One full-host-setup script: OS, k3s, disks, Cloudflare hooks, backend deploy.
- Workspace image defined alongside: slim Debian family, basic toolchain with apt.
- k3s manifests for backend, per-workspace containers, routing; kind runs the same manifests locally.

Open: script and manifest detail at build.
