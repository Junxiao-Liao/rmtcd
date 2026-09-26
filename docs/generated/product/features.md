# features (generated, non-tech)

> Generated from `docs/proposal.md`. Human-maintained for tier meaning; agents: enforce, do not redefine tiers here.

Purpose: define normal vs premium capability matrix in product terms.

Owns: tier names, capability matrix (storage, shell, extensions, server use, limits).
Owns not: auth mechanics, roles implementation, admin APIs (see `backend`).

Locked:
- Separate non-tech doc; capability-matrix scope.
- Premium: files on server, native shell/terminal, curated LSP + highlight allowlist (curation, not sandbox). Normal: public-repo ephemeral, light editor, no shell.
- Extension restriction is managed IDE policy; container isolation is the security boundary.

Open: limit values, upgrade flow (out of scope for now).
