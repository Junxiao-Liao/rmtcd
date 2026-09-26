# architecture (generated)

> Generated from `docs/proposal.md`. Agents: keep up to date with code.

Purpose: map components (browser, backend, compute, storage) and request flows.

Owns: component list, interactions, flows, doc map.
Owns not: versions (see `tech-stack`), API shapes (see `backend`), provisioning (see `operations`).

Locked:
- Angular control UI -> Rust backend (auth + byte-forwarding) -> per-workspace code-server (subdomain with opaque ID, top-level tab, no iframe). Containers private.
- Native IDE terminal only; no backend-proxied user exec path.
- Create and open are separate: create provisions container + empty disk with no session; open ensures the container runs and sets the workspace session cookie, and the tab loads with no URL secret.

Open: endpoint request/response detail at scaffold.
