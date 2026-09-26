# visual (generated)

> Generated from `docs/proposal.md`. Agents: keep up to date with code.

Purpose: define the Angular UI's overall visual style.

Owns: palette, type, density, component look.
Owns not: page layouts (see `pages`), Tailwind setup (see `structure`).

Locked:
- Tailwind under the hood, but the look must be a custom identity — never the obvious default Tailwind/LLM style (default palette, gradient hero, generic cards everywhere). Dark-first theme; dense, sharp, utilitarian.
- Palette follows the VS Code Dark+ terminal: near-#1E1E1E surfaces, terminal green accent, ANSI status colors.
- Type is the system stack (UI + mono), zero webfont weight — exactly how VS Code renders.

Open: none. No signature element — this is a personal tool, not a brand.
