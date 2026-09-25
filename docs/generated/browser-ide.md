# browser-ide (generated)

> Generated from `docs/proposal.md`. Agents: keep up to date with code.

Purpose: define Full workbench client experience without drifting into runtime or ops.

Owns: panels (explorer, tabs, search, git, editor, terminal, sync), attach protocol usage, premium vs normal UX difference.
Owns not: container/server lifecycle (see `workspace-runtime`), hosting (see `operations`).

Locked:
- Full panels.
- Premium: per-container vscode server, LSP + syntax-highlight extensions only.
- Normal: light editor only, ephemeral clone, no vscode server, no LSP.
- Overrides old proposal non-goal (no extensions) for premium only.

Open: panel specifics, git UX, sync button behavior.
