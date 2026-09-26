# workspace-runtime (generated)

> Generated from `docs/proposal.md`. Agents: keep up to date with code.

Purpose: define per-user/project runtime state and execution in one place.

Owns: premium disk lifecycle, normal browser-memory repo handling, container lifecycle, code-server process config/health, mounts and limits.
Owns not: EC2/host provisioning (see `operations`), client UX (see `browser-ide`), wrapper interfaces (see `tech-stack`).

Locked:
- Combined storage + compute doc.
- Premium disk persistence on real filesystem volume (EBS first, cheapest workable type, provisioned through the Storage adapter so other platforms can swap in); S3 backup deferred, not needed for now. Normal repos live only in browser memory, fetched client-side from public hosts; the backend serves only app static assets. No backend clone, no server/LSP/shell.
- Create asks for a name only and starts as an empty disk; size and quota come from admin config; the user clones via the terminal.
- Workspace image: slim Debian family with basic toolchain including apt; users add the rest via shell.
- Shell via native VS Code terminal only; no backend user-facing shell path.
- Stop/start is idle timeout (15 minutes, disk retained, shell processes lost) plus admin control; users get no stop/start buttons. Deleting a workspace deletes its disk too.
- Runtime owns code-server lifecycle (start, health, shutdown); ops owns image and host.
- Quotas: normal has no workspace or container; premium per-workspace quota is admin-configurable, defaulting small (0.5 vCPU, 1 GB RAM, 5 GB disk). Workspace count per user is admin-configurable too, defaulting to one.

Open: volume shapes.
