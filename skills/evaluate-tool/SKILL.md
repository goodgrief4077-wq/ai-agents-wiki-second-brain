---
name: evaluate-tool
description: Use when the user asks "should I try X", "is X worth it", "check out this repo", "benchmark X", or before installing any new dev tool: a staged check (overlap, signals, smoke test, deep review) so nothing is adopted without being run. Do not use for onboarding a skill stack (use skill-stack-onboard) or for reviewing your own code.
---

# Evaluate Tool

Written after a tool that reviewed clean on paper (strong CI, strong docs, strict
AGENTS.md discipline) still "did not work well" in real use and was deleted the
same day. Static code review does not
predict usability. **Never skip straight to deep review — run it, then read it.**

Four stages, each cheap enough to bail out early. Do not skip a stage forward.

## Stage 0 — Overlap check (30 sec)

Read `<tool-ledger>` (your evaluation ledger; row format at the bottom of this
file) and your notes on the current tool stack first.

- Does something already in the stack do this job?
- Has this exact tool already been tried and logged?

If yes to either, and the existing tool currently works: **default reject**, state
the overlap, stop here. Only continue if the user names a concrete differentiator
the existing tool lacks.

## Stage 1 — Cheap signals (2 min)

Pull repo metadata, don't read code yet:

```bash
gh api repos/<owner>/<repo> --jq '{stars:.stargazers_count, open_issues:.open_issues_count, forks:.forks_count, pushed_at:.pushed_at, created_at:.created_at, license:.license.spdx_id}'
```

Red flags that end evaluation here: no commits in 6+ months while claiming active
development, single commit history ("v0.1 initial" and nothing since), no license,
open-issue count that dwarfs stars (nobody maintaining it), or a README describing
features the repo's file tree doesn't contain.

## Stage 2 — Smoke test (10-15 min, HARD GATE)

**Do not go to Stage 3 until this passes.** This is the stage that gets skipped
when a tool looks strong on paper.

Run the tool's one core advertised workflow, once, on a real small task — not a
`--help` screen, not reading the README's examples. Prefer the least invasive way to
try it before a system-wide install: `pnpm dlx`/`uvx`/a throwaway venv/a Docker container/
a git clone run in place (pnpm only, never npm or npx). Only do a global/system install if the tool has no
throwaway mode.

Judge pass/fail only, not quality:
- Did it complete the one thing it promises, on real input, without crashing or
  hanging?
- Was the output actually usable, not just present?

Fail → uninstall/delete immediately, log it (Stage 4), stop. Do not write up a full
review of a tool that failed its own smoke test — that's the exact waste this skill
exists to prevent.

## Stage 3 — Deep review (only if Stage 2 passed and real adoption is on the table)

Now code quality is worth the time:

- Clone it, read CI workflows (`.github/workflows/`), test coverage/structure
- Read its own AGENTS.md/CONTRIBUTING for engineering discipline (dependency policy,
  test requirements, review process)
- Check the install method for security (checksum-verified download vs blind
  curl\|sh, telemetry defaults, what it touches on the system)
- Docs coverage — is there more than a README?

Compare against the compound-engineering skill's bar as a reference point: planning/
review discipline, test rigor, docs depth. Not every good tool needs CE's exact
brainstorm→plan→work→review→compound loop — that's a process layer for a coding
agent to use, not a requirement for the tool itself — but the bar for "is the
engineering disciplined" transfers.

## Stage 3.5 — Scope-check before porting any practice (HARD GATE if porting)

Stage 3's deep review often surfaces a practice worth keeping even when the tool
itself is rejected or deleted (for example git-safety rules, a checksum-verified installer or a CI matrix). **Before writing a ported practice into
CLAUDE.md, a skill, or any repo config, check the scope it was written for and
whether that scope actually matches where you're about to apply it:**

- What specific situation was the source tool's rule solving? (e.g. a
  "never `git stash`" rule exists for its own concurrent-multi-agent-worktree dev
  model — several agents editing the same checkout at once.)
- Does that situation actually hold everywhere you're about to apply the rule, or
  only in a narrower case (a specific repo, a specific workflow)?
- If narrower: scope the ported rule explicitly to that case in the text itself
  (name the repo/condition it applies to) rather than writing it as an unscoped
  global default. A rule that's correct-but-narrow, applied globally, causes real
  friction — refusing a safe `git stash` in a solo session because a rule written
  for concurrent editing got pasted in unscoped,.

This is a hard gate, not a suggestion: don't write a ported rule into a global
file (CLAUDE.md, a skill) without stating the scope it applies to. If genuinely
universal (e.g. "verify checksums before running a downloaded installer"), say so
explicitly — that's a real global, not a skipped check.

## Stage 4 — Decision + log (always, even on rejects)

One dated line appended to `<tool-ledger>`, never overwritten. If your notes are
write-guarded, submit the row through your proposal tool (`<memory-propose-cmd>`)
and tell the user the proposal file name:

```
| YYYY-MM-DD | tool name | stage reached | verdict | one-line why |
```

Verdict is one of: `adopted`, `adopted-with-caveats`, `rejected-stage0-overlap`,
`rejected-stage1-signals`, `rejected-stage2-smoke-test`, `rejected-stage3-review`.

The point of logging rejects too: the next time this tool (or a rebrand or fork of
it) comes up, Stage 0 catches it in 30 seconds instead of
repeating the full cycle.

## Gotchas
- Never write a deep review of a tool that failed its smoke test; log it and stop.
- Never skip Stage 2 because the README or code looks strong.
- Do not write a ported practice into a global file without stating the scope it was written for (Stage 3.5).
- If the ledger is write-guarded, do not write the row directly; propose it and name the proposal file to the user.
- Prefer a throwaway run (pnpm dlx, uvx, venv, container, clone in place) over a system-wide install.

## Checklist before giving a verdict
- [ ] Stage 0 overlap checked against the ledger and the current tool stack
- [ ] Stage 1 signals pulled, red flags named
- [ ] Stage 2 smoke test run on a real small task, pass or fail stated
- [ ] Stage 3 and 3.5 done only if Stage 2 passed
- [ ] Verdict is one of the listed values and the ledger row was proposed
