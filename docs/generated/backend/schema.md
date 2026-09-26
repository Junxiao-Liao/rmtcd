# schema (generated)

> Generated from `docs/proposal.md`. Agents: keep up to date with code. Schema changes always keep RDB normal forms.

Purpose: track the Postgres tables behind the Rdb trait.

Owns: table list, columns, relations, migration order.
Owns not: trait signatures (see `devops/tech-stack`), API contracts (see `backend`).

Locked:
- Tables cover users, workspaces, quotas, usage, invites; all in normal form.

Open: columns, keys, exact DDL at scaffold; migrations via sqlx-migrate.
