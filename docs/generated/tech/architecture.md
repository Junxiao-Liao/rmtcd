# architecture (generated)

> Generated from `docs/proposal.md`. Agents: keep up to date with code.

Purpose: map components (browser, backend, compute, storage) and request flows.

Owns: component list, interactions, flows, doc map.
Owns not: versions (see `tech-stack`), API shapes (see `backend`), provisioning (see `operations`).

Locked:
- Angular control UI -> gateway -> per-workspace code-server (subdomain, top-level tab, no iframe). Containers private.
- Native IDE terminal only; no backend-proxied user exec path.
- Backend enforces auth/roles + project grants; `features` defines tiers.

Open: launch/session sequence details, sync semantics, reconnect behavior.
