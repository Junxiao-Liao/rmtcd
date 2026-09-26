# browser-ide (generated)

> Generated from `docs/proposal.md`. Agents: keep up to date with code.

Purpose: define Full workbench client experience without drifting into runtime or ops.

Owns: panels (explorer, tabs, search, git, editor, native terminal, sync), workspace open flow, premium vs normal UX difference.
Owns not: container/server lifecycle (see `workspace-runtime`), hosting (see `operations`).

Locked:
- Premium IDE is code-server, running privately in the workspace container, never exposed directly; the Rust backend forwards to it after auth.
- Per-workspace subdomain (`w-<workspace-id>.workspaces.example.com`), opened as top-level page / new tab. No iframe.
- Terminal is the native VS Code integrated terminal only. No separate Angular/xterm shell.
- Language support via normal VS Code extension/LSP ecosystem (highlight, IntelliSense, diagnostics, hover, goto-def, quick fixes).
- No extension allowlist: users may install what they want; the container is the only security boundary.
- Sync: normal is client-side git via isomorphic-git over any public URL (in-memory filesystem, pull only, branch picker); premium works directly on the container filesystem, no S3 backup for now.
- Premium panels are stock code-server (explorer, tabs, search, git, editor, terminal); no custom panels day one.
- Normal editor is plain Monaco with tokenization only and a file list + tabs; no language servers. Browser-side repos warn past 50 MB and refuse past 200 MB.
- Reconnect relies on stock code-server behavior: the server keeps state, the browser auto-reconnects and resumes; manual reload only if the socket is dead.
- Angular shell holds workspaces, open, account, and admin; the normal light editor lives there too.

Open: none; git is client-side isomorphic-git, pull only. Scaffold detail only.
