# browser-ide (generated)

> Generated from `docs/proposal.md`. Agents: keep up to date with code.

Purpose: define Full workbench client experience without drifting into runtime or ops.

Owns: panels (explorer, tabs, search, git, editor, native terminal, sync), workspace open flow, premium vs normal UX difference.
Owns not: container/server lifecycle (see `workspace-runtime`), hosting (see `operations`).

Locked:
- Premium IDE is code-server, running privately in the workspace container, never exposed directly; authenticated gateway proxies it.
- Per-workspace subdomain (`w-<workspace-id>.workspaces.example.com`), opened as top-level page / new tab. No iframe.
- Terminal is the native VS Code integrated terminal only. No separate Angular/xterm shell.
- Language support via normal VS Code extension/LSP ecosystem (highlight, IntelliSense, diagnostics, hover, goto-def, quick fixes).
- Extensions use a managed allowlist (default deny, pinned versions, baked into image). This is product curation, not a security boundary — shell users can already run arbitrary code in their container; the real boundary is container isolation (see `operations`).

Open: panel specifics, git UX, sync meaning (git vs backup vs settings — must not conflate).
