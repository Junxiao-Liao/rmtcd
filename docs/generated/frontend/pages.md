# pages (generated)

> Generated from `docs/proposal.md`. Agents: keep up to date with code.

Purpose: list Angular UI pages with each page's brief layout and components.

Owns: page list, per-page layout, component inventory.
Owns not: visual identity (see `visual`), folder layout (see `structure`), premium IDE panels (see `browser-ide`).

Locked:
- Shell holds workspaces, open, account, and admin; the normal light editor lives there too. Workspaces page is cards (name, status dot + text, open button, hours mini readout) with a name-only create dialog; delete lives in the admin workspaces section only; admin uses sidebar sections. Auth is one page: login panel, flipped to set-password mode by an invite token in the URL. Editor and panel details follow VS Code OSS rather than re-specifying (tree nav, tabs, status behavior).

Open: none. The open state names what is happening (starting, waking from idle stop) and hands off; no fake progress.
