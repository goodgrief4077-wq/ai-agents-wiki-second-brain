---
name: gstack
description: Use when the user says "use gstack", "install gstack", "upgrade gstack", "which gstack skill", or asks for a structured idea-to-ship flow (office hours, plan reviews, PR review, QA, ship) from the garrytan/gstack skill set. Maps each stage of a build to the gstack skill that covers it and lists install, privacy and safety facts. Do not use to browse the web on a machine where another browser skill is required, or as a replacement for a project's own tests.
license: MIT
metadata:
  version: "1.0"
  updated: "2026-10-25"
  source: "github.com/garrytan/gstack README and skill folders, main at commit e66c43c (2026-10-25), version series 1.91, MIT"
---

# gstack

gstack is an MIT-licensed set of slash-command skills (Markdown) that makes a coding agent act like a small team: a product challenger, an engineering reviewer, a designer, a QA lead, a security auditor and a release engineer. It is third-party code with its own installer. This skill is a map and a safety note, not a copy; read the upstream skill before first use.

## Pick the skill by stage

| Stage | Skill | What it does (upstream descriptions, shortened) |
|---|---|---|
| Idea | `/office-hours` | Two-mode idea challenge |
| Spec | `/spec` | Turns vague intent into a precise spec in five phases, as a backlog-ready issue |
| Plan review | `/plan-ceo-review`, `/plan-eng-review`, `/plan-design-review`, `/plan-devex-review` | Scope, architecture, design and developer-experience reviews of a plan |
| Plan, all reviews | `/autoplan` | Runs the four reviews in sequence with automatic decisions |
| Debug | `/investigate` | Root-cause debugging |
| Review | `/review` | Pre-landing PR review |
| Test | `/qa` (fixes), `/qa-only` (reports), `/test-audit` | Browser, API, CLI, job and webhook bug hunting; finds low-value or duplicate tests |
| Security | `/cso` | Security audit |
| Ship | `/ship`, `/land-and-deploy`, `/canary`, `/document-release` | Tests, diff review, version, changelog, PR; then deploy and post-deploy watch |
| Safety | `/careful`, `/freeze`, `/unfreeze`, `/guard` | Destructive-command warnings; limit edits to one directory |
| Design | `/design-consultation`, `/design-shotgun`, `/design-html`, `/design-review` | Design system, variants, HTML, visual QA |
| Other | `/retro`, `/context-save`, `/context-restore`, `/diagram`, `/make-pdf`, `/benchmark`, `/health` | Retrospective, save and restore context, diagrams, PDF, performance, code-quality dashboard |

The README's own end-to-end prompt is: load gstack, run `/autoplan`, implement the plan, then run `/ship`. For planning only: `/office-hours` then `/autoplan`, save the plan, do not implement.

## Install and upgrade
1. Requirements per the README: Claude Code, Git, Bun 1.4.2 or newer (setup refuses anything older than 1.3.3). Check `bun --version` first.
2. Read upstream `setup` and `SKILL.md` before running anything. `./setup` builds a binary and downloads a Chromium.
3. Clone into its own folder as the README says (`~/.claude/skills/gstack`, `git clone --single-branch --depth 1`), then run `./setup` from there. Never clone inside a project.
4. Verify: type `/office-hours`; it must be recognised.
5. Upgrade with `/gstack-upgrade` (it detects a global or vendored install). Team mode is `./setup --team` run from inside the repo.
6. Other agent harnesses are supported through `./setup --host <name>`; the README has the table. Some harnesses use prefixed names such as `/gstack-review`.

## Privacy
- Telemetry is opt-in and off by default; `gstack-config set telemetry off` turns it off.
- The update check is on by default, independent of telemetry.
- A one-time consent prompt appears before artifact or brain sync is used. Answer it deliberately.

## Gotchas
- Old shelf copies are often the 1.x browser-only skill. The full set (spec, plan reviews, ship, safety) is upstream only.
- Use the browser skill that belongs to your environment if your setup requires one; do not let gstack's `/browse` override it.
- `/autoplan` decides for you. Read the decisions it logs; do not accept them blind.
- A gstack finding that changes behaviour belongs back in the spec, not only in the code.
- Skills evolve fast (the repo changes daily). Re-check the upstream skill description before relying on a flag.
