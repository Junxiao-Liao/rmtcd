# workspace-runtime (generated)

> Generated from `docs/proposal.md`. Agents: keep up to date with code.

Purpose: define per-user/project runtime state and execution in one place.

Owns: disk (premium) vs ephemeral public-repo clone (normal) lifecycle + sync, container lifecycle, exec protocol, vscode-server start/attach/shutdown.
Owns not: EC2/host provisioning (see `operations`), client UX (see `browser-ide`), wrapper interfaces (see `tech-stack`).

Locked:
- Combined storage + compute doc.
- Premium disk persistence; normal ephemeral clone.
- Containers; runtime owns vscode-server lifecycle.

Open: volume shapes, idle teardown, exec protocol details.
