---
name: superpowers
description: Use when the user says "use superpowers", "install superpowers", "which superpowers skill", or wants the obra/superpowers workflow (brainstorm, worktree, plan, subagent build, TDD, review, finish branch) for a coding task. Maps each step of a build to the superpowers skill that covers it and lists install, privacy and gotcha facts. Do not use for a one-line fix or when the project already enforces another full methodology.
license: MIT
metadata:
  version: "1.0"
  updated: "2026-10-25"
  source: "github.com/obra/superpowers README and skills folder, main at commit 2ce8aa1, release v7.0.1 (2026-10-21), MIT"
---

# Superpowers

Superpowers is an MIT-licensed software-development methodology delivered as composable skills plus a starter skill (`using-superpowers`) that makes the agent check for a relevant skill before any task. The skills trigger on their own; the user does not call them by hand. This skill is a map and a safety note, not a copy; read the upstream skill before relying on it.

## The workflow, in order (from the README)
1. `brainstorming`: before building anything, draws out what and why, plays understanding back; small changes agreed in chat, projects get a written design.
2. `using-git-worktrees`: after design approval, makes an isolated branch workspace and checks a clean test baseline.
3. `writing-plans`: splits the approved design into small tasks with exact file paths, code and verification steps.
4. `subagent-driven-development` (fresh subagent per task, review after each; most thorough) or `executing-plans` (inline, one review at the end).
5. `test-driven-development`: red, green, refactor; code written before its test is deleted.
6. `requesting-code-review`: between tasks, issues by severity, critical ones block.
7. `finishing-a-development-branch`: verifies tests, offers merge, PR, keep or discard, cleans the worktree.

## Other skills in the repo
`systematic-debugging`, `verification-before-completion` (run the checks before claiming done), `dispatching-parallel-agents`, `receiving-code-review`, `writing-skills`, `diagnosing-superpowers` (reads a session transcript to explain misbehaviour and can package a scrubbed bug-report bundle).

## Install
1. Install per harness; each harness needs its own install. Claude Code: `/plugin install superpowers@claude-plugins-official` (official marketplace). The README also covers Codex, Cursor, Gemini CLI, OpenCode, Pi, Copilot CLI, Hermes and others.
2. Verify in a new session: the agent should announce a skill before starting a build task.
3. Update through the harness; many update automatically.

## Privacy
By default the optional visual companion in `brainstorming` loads the project logo from the vendor site, and that request includes the installed Superpowers version. Check the README's telemetry section for how to turn it off before using the visual companion.

## Gotchas
- The skills are mandatory workflows, not suggestions; a small task can feel heavy. Say "skip brainstorming, this is a one-line fix" or do not use it for trivia.
- It overlaps with other full methods (Spec Kit, BMad, gstack). Use one planning method per project to avoid two plans.
- Skills fire from descriptions; a misfire or silence is debugged with `diagnosing-superpowers`, not by editing skills.
- Re-check the README before relying on an install command; harness instructions change between releases.
