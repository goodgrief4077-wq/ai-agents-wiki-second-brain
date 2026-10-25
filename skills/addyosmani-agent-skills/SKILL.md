---
name: addyosmani-agent-skills
description: Use when the user says "use Addy Osmani skills", "install agent-skills", "which agent-skills skill", or wants a lifecycle set of engineering skills (spec, plan, build, test-driven development, code review, git workflow, ship) from the addyosmani/agent-skills repo. Maps each stage to the upstream skill and lists install, privacy and safety facts. Do not use as a replacement for a project's own tests or CI.
license: MIT
metadata:
  version: "1.0"
  updated: "2026-10-25"
  source: "github.com/addyosmani/agent-skills README and skill folders, main at commit aeac41d (2026-10-13), plugin version 0.6 series, MIT"
---

# addyosmani-agent-skills

An MIT-licensed pack of 25 Markdown skills (24 lifecycle skills plus one meta skill) by Addy Osmani. Each skill is a structured workflow with steps, verification gates and a table of excuses agents use to skip steps. Nine slash commands map to the lifecycle. Third-party code. This skill is a map and a safety note, not a copy; read the upstream skill before first use.

## Pick the skill by stage

| Stage | Command | Skill | What it does (own words) |
|---|---|---|---|
| Define | `/spec` | `spec-driven-development` | Write the spec before code |
| Define | | `idea-refine`, `interview-me` | Sharpen a vague idea; one-question-at-a-time interview |
| Plan | `/plan` | `planning-and-task-breakdown` | Ordered, small tasks |
| Build | `/build` | `incremental-implementation` | Thin verifiable slices |
| Test | `/test` | `test-driven-development` | Red-green-refactor for logic, bug fixes and behaviour changes |
| Debug | | `debugging-and-error-recovery` | Systematic root-cause debugging |
| Review | `/review` | `code-review-and-quality` | Multi-axis review before merge, for your own, an agent's or a human's code |
| Simplify | `/code-simplify` | `code-simplification` | Clarity refactors without behaviour change |
| Version | | `git-workflow-and-versioning` | Commit, branch and conflict habits; turns a messy tree into atomic commits |
| Ship | `/ship` | `shipping-and-launch`, `ci-cd-and-automation` | Pre-launch checklist, pipelines and quality gates |
| Other | | `security-and-hardening`, `performance-optimization`, `api-and-interface-design`, `frontend-ui-engineering`, `documentation-and-adrs`, `context-engineering` | Topic skills that activate by task |
| Meta | | `using-agent-skills` | Decides which skill applies |

`/build auto` plans once, then implements every task in one approved pass; each task is still test-first and committed alone. Where a built-in command shares a name (`/review`), Claude Code needs the namespaced form from the README.

## Install
1. Read the README install section and the skill you want before installing.
2. Claude Code, as the README states: `/plugin marketplace add addyosmani/agent-skills`, then `/plugin install agent-skills@addy-agent-skills`.
3. Any agent, as the README states: `npx skills add addyosmani/agent-skills --list` to browse, then `--skill <name>` for one skill (for example `test-driven-development`).
4. Codex, Gemini CLI, Copilot and others have their own commands in the README and its docs folder.
5. Verify by invoking one skill by name; it must be recognised.

## Privacy
- Plain Markdown plus plugin hooks and scripts in the repo; read the hooks folder before enabling a plugin install.
- No telemetry is described in the README. Check the installer's own prompts.

## Gotchas
- A single-skill npx install copies only that skill folder, not the shared references folder, so linked checklists may be missing (the README tracks this as an open issue).
- The plugin marketplace clones over SSH by default; the README gives an HTTPS workaround.
- Commands are Claude Code features; other hosts invoke skills by name.
- Review and test skills raise the bar; they do not replace your CI. Keep your own test run as the proof.
- Skill list and versions move; re-check upstream descriptions before relying on one.
