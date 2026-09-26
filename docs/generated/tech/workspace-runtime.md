# workspace-runtime (generated)

> Generated from `docs/proposal.md`. Agents: keep up to date with code.

Purpose: define per-user/project runtime state and execution in one place.

Owns: disk (premium) vs ephemeral public-repo clone (normal) lifecycle + sync, container lifecycle, code-server process config/health, mounts and limits.
Owns not: EC2/host provisioning (see `operations`), client UX (see `browser-ide`), wrapper interfaces (see `tech-stack`).

Locked:
- Combined storage + compute doc.
- Premium disk persistence on real filesystem volume (not S3); S3 for archives/backups/exports only. Normal ephemeral clone with TTL, no server/LSP/shell.
- Shell via native VS Code terminal only; backend Exec removed as user-facing shell path.
- Runtime owns code-server lifecycle (start, health, shutdown); ops owns image and host.

Open: volume shapes, PVC retention/restore procedure, idle teardown (must not kill builds on browser close), resource quotas.
