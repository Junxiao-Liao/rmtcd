# architecture (generated)

> Generated from `docs/proposal.md`. Agents: keep up to date with code.

Purpose: map components (browser, backend, compute, storage) and request flows.

Owns: component list, interactions, flows, doc map.
Owns not: versions (see `tech-stack`), API shapes (see `backend`), provisioning (see `operations`).

Locked:
- Browser -> backend -> workspace-runtime -> operations layering.
- Backend enforces auth/roles; `features` defines tiers.

Open: sequence details for shell attach, sync, vscode-server attach.
