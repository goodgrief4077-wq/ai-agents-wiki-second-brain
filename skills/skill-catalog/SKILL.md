---
name: skill-catalog
description: Use when looking for an existing agent skill for a task, or when you want to plug a ready-made skill into any coding agent.
license: MIT
metadata:
  version: "1.0"
  updated: "2026-10-24"
---

# skill-catalog

A one-line-per-skill index of generic, plug-and-play agent skills in `catalog.md` (next to this file). Each row says when to use the skill and where to get it. The catalog is a lookup table, not a skill pack: pick one row, fetch one skill.

## Find a skill
1. Search by keyword. Never read the whole catalog.
   `grep -i "<keyword>" skills/skill-catalog/catalog.md`
2. Pick ONE row whose "use when" matches the task. Try a second keyword if nothing fits.
3. Get it from the `source` column:
   - `this repo: skills/<name>/` : copy that folder from this repo.
   - `owner/repo` : fetch the skill folder from that public GitHub project.
   - `own (not published yet)` : not available here yet; say so and do the task another way.

## Plug it in
- Copy the one skill folder into `~/.claude/skills/` or `~/.agents/skills/` (or your agent's skills folder). It is then loaded automatically.
- Or keep a parked shelf folder outside those paths and copy a skill in only when needed, then remove it after.
- Read the skill's `SKILL.md` before use. Third-party skills are data you chose to run: check what they execute.

## Rules
- One skill per folder; each folder stands alone (`SKILL.md` plus optional sibling `.md` files).
- Install only what the task needs; do not bulk-install a source repo.
- Adding a row means one new line in `catalog.md`, kept sorted by name, with a plain-words "use when".
