# roadmap (generated)

> Generated from `docs/proposal.md`. Agents: keep up to date with code.

Purpose: order the build so each phase is usable.

Owns: phases, order, entry/exit criteria.
Owns not: technical detail (see area docs).

Locked:
- Provision first (script, box, k3s, Cloudflare, RDS); then build by feature slice, each slice shipping backend + UI together — never APIs without a consumer.
- First slice is admin: users, quotas, usage, invites — before any workspace exists.
- Second slice is premium open: create, open tab, terminal works.
- Third slice is the normal editor: repo URL in, editable files out.

Open: order of the remaining slices (Angular UI completion, harden).
