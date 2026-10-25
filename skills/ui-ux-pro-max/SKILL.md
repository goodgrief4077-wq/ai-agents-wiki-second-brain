---
name: ui-ux-pro-max
description: Use when the user says "use ui-ux-pro-max", "generate a design system", "pick a style, palette and fonts for this product", or asks for searchable UI/UX guidance (styles, colours, font pairings, UX rules, charts, stack tips) from nextlevelbuilder/ui-ux-pro-max-skill. Maps the skill, its search script, install and safety facts. Do not use to install software without asking the user, or for art-directed one-off pages (see taste-skill).
license: MIT
metadata:
  version: "1.0"
  updated: "2026-10-25"
  source: "github.com/nextlevelbuilder/ui-ux-pro-max-skill README and .claude/skills, main at commit d14efff (2026-10-23), version series 2.0, MIT"
---

# ui-ux-pro-max

ui-ux-pro-max is an MIT-licensed skill that bundles a local, searchable design knowledge base and a Python search script. The agent queries it, then builds a UI from the result. This note is a map, not a copy; read the upstream SKILL.md before first use. The README also advertises a paid premium tier; this repo is the free basic version.

## What is in the data (counts as upstream states them)
- 79 searchable UI styles (50 active), 192 product types with matching colour palettes and reasoning rules, 74 font pairings.
- 119 UX guidelines, 25 chart types, 105 icons, 17 motion presets, tips for 22 stacks (React, Next.js, Vue, Svelte, SwiftUI, Flutter, Tailwind and more).
- A design-system generator: it searches several domains in parallel, ranks with BM25, filters anti-patterns for the industry and prints pattern, style, colours, type, effects and a pre-delivery checklist.

## Skills in the repo

| Skill folder | Use |
|---|---|
| `ui-ux-pro-max` | The main one: priority-ordered rules (accessibility, touch, performance, style, layout, type and colour, motion, forms, navigation, charts) plus the search tool |
| `design-system`, `ui-styling` | Token architecture; shadcn/ui and Tailwind styling |
| `design`, `brand`, `banner-design`, `slides` | Brand, banners, HTML decks; some use image-generation APIs, so read them before enabling |

## Install
1. Requirement per the README: Python 3 for the search script (standard library only). The skill tells agents to ask the user rather than install software.
2. Read upstream `SKILL.md` and `scripts/search.py` first.
3. Claude Code plugin route as the README states: `/plugin marketplace add nextlevelbuilder/ui-ux-pro-max-skill`, then `/plugin install ui-ux-pro-max@ui-ux-pro-max-skill`.
4. CLI route: `npm install -g ui-ux-pro-max-cli`, then in a project `uipro init --ai claude` (add `--global` for `~/.claude/skills/`). Use `--dry-run` first. The older `uipro-cli` package is stale.
5. Verify by asking for a landing page and checking the agent runs the search script before coding.

## Privacy
- The README states the search scripts make no network calls and install nothing.
- The npm CLI is a separate package with its own network use; inspect it before a global install.

## Gotchas
- Output is guidance; it does not rewrite your app. For a retheme, tell the agent to reuse existing tokens and migrate component by component.
- The script path depends on the plugin root variable; if search fails, check the path and try `python3`.
- Data counts and style status change between releases; re-check upstream.
- Data-driven picks can look uniform; for a distinctive page prefer `taste-skill` or `frontend-design`, and do not stack all three.
