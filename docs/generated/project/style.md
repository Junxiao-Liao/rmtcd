# style (generated)

> Generated from `docs/proposal.md`. Agents: keep up to date with code.

Purpose: record shared coding style across frontend and backend.

Owns: paradigm, file granularity, shared rules.
Owns not: area layouts (see `frontend/structure`, `backend/structure`, `devops/structure`).

Locked:
- Elegant FP style: pure functions where possible, data over hidden state, explicit effects at the edges.
- One purpose per file; files stay small and orthogonal.
- Schema changes always keep RDB normal forms; the schema doc tracks every table.

- Toolchain defaults: rustfmt + clippy, prettier + eslint.

Open: per-language idioms at scaffold.
