# structure (generated)

> Generated from `docs/proposal.md`. Agents: keep up to date with code. Approximate on purpose — doc phase cannot be impl-complete.

Purpose: sketch the Angular shell layout.

Owns: feature folders, shared pieces, styling hookup.
Owns not: page layouts (see `pages`), visual identity (see `visual`), backend layout (see `backend/structure`).

Locked:
- Standalone components only, no NgModules.
- Feature folders: workspaces, open, account, admin, editor, shared. Each feature owns its components; cross-feature code lives in shared.
- Tailwind for styling; custom identity defined in `visual`.

Open: file-level detail at scaffold.
