---
name: bmad
description: Use when the user says "use BMad", "install BMAD", "BMad method", "which BMad skill", or wants agile AI-driven development (brief, PRD, architecture, build, review, retrospective) from bmad-code-org/BMAD-METHOD. Maps each stage to the BMad skill that covers it and lists install lines, the stable versus preview split, and gotchas. Do not use for a small one-off change that needs no planning, or to run two planning methods on one project.
license: MIT
metadata:
  version: "1.0"
  updated: "2026-10-25"
  source: "github.com/bmad-code-org/BMAD-METHOD README and skills folder, main at commit 61e01f8 (2026-10-18), stable release v6.12.4 (2026-10-14), MIT"
---

# BMad Method

BMad ("Agile AI-driven development") is an MIT-licensed method delivered as skills. It sizes the process to the work: a small change goes straight to build, a large one gets a brief, a PRD, architecture and UX first. Decisions are written down and carried forward as context. This skill is a map, not a copy; read the upstream docs before relying on a command.

## Two lines, pick one
- **Stable v6.12** (frozen except bug fixes): needs Node 20.12+, Python 3.10+ and `uv`. Install in the project with `npx bmad-method install`. Invoke `bmad-build` with the change; run `bmad-help` for the next step.
- **V7 preview alpha** (this is the repo's main branch; skills and install path change often, breaking changes expected): `npx skills add bmad-code-org/BMAD-METHOD --skill '*'`, or the Claude Code plugin marketplace `bmad-code-org/bmad-plugins`, or the Codex plugin marketplace of the same name. Then ask the `bmad` skill to run `bmad setup`; ask `bmad status` for versions. The README gave a v7 release estimate that had already passed when this was written: check which line is current before choosing.

## Pick the skill by stage (v7 preview names)
| Stage | Skill |
|---|---|
| Clarify | `bmad-brainstorming`, `bmad-product-brief`, `bmad-prfaq`, `bmad-deep-recon`, `bmad-advanced-elicitation` |
| Plan | `bmad-prd`, `bmad-architecture`, `bmad-ux`, `bmad-project-context` |
| Build | `bmad-build` (one change), `bmad-build-auto` |
| Verify | `bmad-code-review`, `bmad-review`, `bmad-qa-generate-e2e-tests` |
| Learn | `bmad-retrospective` |
| Perspectives | `bmad-agent-analyst`, `-pm`, `-po`, `-architect`, `-ux-designer`, `-dev`; `bmad-party-mode` (multi-agent discussion) |
| Guidance | `bmad` (hub, status, setup), `bmad-customize` |

Official add-on modules (separate repos): BMad Builder (build skills and agents), Creative Intelligence Suite, Test Architect (enterprise testing), Loop (builds and retros an epic unattended), Game Dev Studio.

## Steps for a new change
1. Install one line (above) in the project, not globally mixed with the other line.
2. Say what you want to change to `bmad-build`; for anything vague start at clarify, for a big clear idea at plan.
3. Keep briefs, PRD and architecture files in the repo so decisions are versioned.
4. Run a review skill before merge; run the retrospective after.

## Gotchas
- The README names a trademark file; the code is MIT, the BMad name and logo are not free to reuse.
- Preview skills are renamed and removed between releases; `bmad setup` cleans up renamed skills.
- Overlaps with Spec Kit, superpowers and gstack. Use one planning method per project.
- `bmad-build-auto` and Loop run unattended; review their output before merging, and never let them merge.
- Skill names above are from the preview branch and may differ on stable v6.12.
