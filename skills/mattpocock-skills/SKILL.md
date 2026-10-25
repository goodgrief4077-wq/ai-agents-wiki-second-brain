---
name: mattpocock-skills
description: Use when the user says "use mattpocock skills", "install Matt Pocock skills", "grill me", "which Matt Pocock skill", or wants small composable engineering skills (grilling, spec, tickets, tdd, diagnosing bugs, code review, architecture survey) from the mattpocock/skills repo. Maps each situation to the upstream skill and lists install, privacy and safety facts. Do not use as a replacement for a project's own tests, or when a process-owning framework is already mandated.
license: MIT
metadata:
  version: "1.0"
  updated: "2026-10-25"
  source: "github.com/mattpocock/skills README and skill folders, main at commit 5beb35b (2026-10-19), plugin version 1.3.1, MIT"
---

# mattpocock-skills

An MIT-licensed set of small Markdown skills by Matt Pocock for everyday engineering with a coding agent. The README positions them against process-owning frameworks: each skill is short, composable and meant to be edited. Third-party code. This skill is a map and a safety note, not a copy; read the upstream skill before first use. Background page: `wiki/entities/matt-pocock-skills.md`.

## Pick the skill by situation

| Situation | Skill | What it does (own words) |
|---|---|---|
| Plan is vague | `grill-me` | Agent interviews you hard about a plan; for non-code work too |
| Plan touches a codebase | `grill-with-docs` | Same interview, also writes a shared glossary and decision records |
| Turn talk into a spec | `to-spec` | Synthesises the conversation into a spec on the issue tracker, no interview |
| Split work | `to-tickets` | Thin end-to-end tickets with blocking links, published to the tracker |
| Build | `implement`, `implement-spec` | Implements from a spec or a set of tickets |
| Test-first | `tdd` | Red-green-refactor, with guidance on good and bad tests |
| Something broken | `diagnosing-bugs` | Phase-gated diagnosis loop for hard bugs and slowdowns |
| Review | `code-review` | Reviews changes since a fixed point on two axes, repo standards and spec match, in parallel sub-agents |
| Design health | `improve-codebase-architecture` | Surveys for deepening opportunities and shows an HTML report; a survey, not a rescue |
| PR text | `pr` | Writes the PR body |
| Issue flow | `triage` | Moves issues through triage states and writes agent-ready briefs |
| Other | `handoff`, `teach`, `wayfinder`, `retro`, `research`, `prototype`, `wizard` | Session handoff, learning, navigation, retrospective, research, prototypes |

The folders `in-progress/` and `deprecated/` hold unfinished or retired skills; avoid them. The skills.sh id `request-refactor-plan` does not exist in the current repo; refactor planning now sits in `to-spec`, `to-tickets` and the architecture survey. Check the folder list before quoting a name.

## Install
1. Read the README's install section first; pick ONE route per agent, since a plugin plus a copied install gives every skill twice.
2. Claude Code, as the README states: `claude plugin install mattpocock-skills@claude-plugins-official` (updates itself).
3. Other agents, as the README states: `npx skills@latest add mattpocock/skills -a <agent>`; when asked, include `setup-matt-pocock-skills`. Codex, Copilot and Gemini CLI have their own commands in the README.
4. Run `/setup-matt-pocock-skills` once per repo. It asks for your issue tracker, triage labels and where docs live.
5. Verify by typing `/tdd`; it must be recognised.

## Privacy
- Skills are plain Markdown; read them before installing. The skills.sh route copies editable files into the project.
- The README links a newsletter signup; nothing else is required. Check the installer's own prompts for any analytics.

## Gotchas
- Most skills assume a configured tracker; without the setup step, `to-spec`, `to-tickets` and `triage` have nowhere to publish.
- `to-spec` publishes to a real tracker; confirm the target before running on a shared repo.
- The glossary file naming changed between versions; follow the folder's own convention.
- Names get renamed often (the repo is active). Re-check upstream descriptions before relying on one.
