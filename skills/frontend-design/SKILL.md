---
name: frontend-design
description: Use when the user says "use frontend-design", "make this look designed", "this page looks generic or AI-made", or asks for distinctive visual design (aesthetic direction, typography, layout, UI copy) when building or reshaping a web page or app screen. Maps the anthropics/skills frontend-design skill, its process and its install. Do not use for pure logic work, for accessibility audits alone, or when the brief already fixes a design system you must follow.
license: Apache-2.0
metadata:
  version: "1.0"
  updated: "2026-10-25"
  source: "github.com/anthropics/skills README and skills/frontend-design, main at commit dbd4588 (2026-10-09), skill folder licence Apache-2.0"
---

# frontend-design

`frontend-design` is one example skill in Anthropic's public skills repo. It is a single Markdown file (no scripts) that pushes a coding agent away from templated pages toward a deliberate visual point of view. The skill folder carries its own LICENSE.txt, Apache-2.0. Note: other document skills in the same repo can be source-available, so check the licence per skill folder, never per repo. This note is a map, not a copy; read the upstream file before first use.

## What the skill tells the agent to do

| Part | Idea |
|---|---|
| Ground in the subject | Name the product, audience and main job first (propose one and confirm if the brief is silent); take visual choices from the subject's own world |
| Design principles | Open with the most characteristic thing in that world; type carries personality; short line lengths; structure (rules, numbering, labels) must encode real information |
| Motion | Sparing; one orchestrated moment beats scattered hover and fade effects; motion that answers a user action is fine |
| Process | Write a compact plan first (4 to 6 named colours, type roles, layout idea, principles), test it against the brief, revise anything generic, then build |
| Defaults to avoid | Cream background with serif and clay accent; near-black with one neon accent; broadsheet look; identical rounded cards; stock eyebrow labels and arrows |
| Restraint | Spend boldness in one place; quality floor of responsive, visible focus, reduced motion, accessible contrast |
| Writing | Interface words are design: user language, active voice, one name per action, errors that say how to fix |

The brief always wins: if the user asks for one of the listed "defaults", build it.

## Install
1. Read upstream `skills/frontend-design/SKILL.md` first; it is plain text.
2. Claude Code, as the README states it: `/plugin marketplace add anthropics/skills`, then install the example-skills set with `/plugin install example-skills@anthropic-agent-skills` (or browse via the plugin menu).
3. Or copy only the one folder into `~/.claude/skills/frontend-design/` after reading it.
4. Verify by asking for a landing page and checking that the agent writes a design plan before code.

## Privacy
- No network calls, no scripts, no telemetry: the skill is instructions only.
- The marketplace install pulls the whole example-skills plugin, which holds many skills; copying one folder avoids that.

## Gotchas
- It is taste guidance, not a checker: nothing fails if the agent ignores it. Pair with a real-browser review or a rules audit.
- The plan-review step adds a pass; for a small tweak to an existing page, say "keep the current system" so it does not redesign.
- Upstream edits the skill text over time (the current version names specific colour tells); re-read before relying on a detail.
- Overlaps with `taste-skill` and `ui-ux-pro-max`; pick one lead skill per build, they give conflicting directions.
