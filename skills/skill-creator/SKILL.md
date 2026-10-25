---
name: skill-creator
description: Use when the user says "create a skill", "improve this skill", "test my skill", "benchmark a skill" or "fix the skill description", or asks how Anthropic's skill-creator skill works. Maps its loop (intent, draft, test runs with and without the skill, review, improve, description tuning) and its install, safety and gotcha facts. Do not use as the writing-style guide (use the wiki page writing-effective-agent-skills) or to build an MCP server.
license: Apache-2.0
metadata:
  version: "1.0"
  updated: "2026-10-25"
  source: "github.com/anthropics/skills skills/skill-creator (SKILL.md, agents/, scripts/), main at commit dbd4588 (2026-10-09), Apache-2.0 per the folder's LICENSE.txt"
---

# skill-creator

skill-creator is Anthropic's skill for making and tuning other skills. It is Apache-2.0 licensed (the folder carries its own LICENSE.txt; some other skills in the same repo are not open, so check each folder). This note is a map, not a copy. For how to write a good skill (concise, one job, trigger-rich description), read the wiki page `writing-effective-agent-skills` first; skill-creator adds the test-and-measure machinery around it.

## The loop

1. Capture intent: what the skill does, when it should fire, the output format, and whether it needs test cases.
2. Interview and research: edge cases, inputs, examples, success criteria. Look up similar skills before writing.
3. Draft `SKILL.md`: a name, a description that says when to use it, then the body. Heavy detail goes into sibling reference files, scripts or assets that load only when needed (progressive disclosure).
4. Write a few realistic test prompts and share them with the user.
5. Run each prompt twice in the same turn: once with the skill, once as a baseline (no skill, or the old version when improving).
6. While runs finish, draft checkable assertions; record timing and tokens per run.
7. Grade, aggregate into a benchmark, and open the bundled review viewer so the user can leave per-case feedback.
8. Improve from the feedback: generalise rather than overfit to the test cases, cut instructions that earn nothing, explain the why instead of shouting rules. Re-run into a new iteration folder until the user is happy or progress stops.
9. Optional: blind comparison of two versions by an independent comparer agent.
10. Optional: description optimisation. Write about twenty trigger and non-trigger queries, review them with the user, then run the bundled loop that scores and rewrites the description on a train and test split.

## What is in the folder
- `agents/`: grader, comparator and analyzer prompts.
- `scripts/`: benchmark aggregation, report generation, eval runner, description improver, a validator and a packager that makes a `.skill` file.
- `eval-viewer/`, `references/`, `assets/`: the review UI, schemas and templates.
- It has separate notes for Claude.ai (no subagents, so run tests serially, no baseline) and Cowork.

## Install
The README of anthropics/skills says to add the repo as a plugin marketplace in Claude Code with `/plugin marketplace add anthropics/skills`, then pick a plugin set. Read the plugin contents and the scripts before installing; the eval scripts launch Claude runs and a local viewer. Check the README for the current plugin names, since skill-creator is listed in the example set, not the document set.

## Privacy
- Test runs send your prompts and any files you give them to the model; use non-sensitive test data.
- The description-optimisation loop makes many model calls, which costs tokens and time.

## Gotchas
- Without subagents there is no clean baseline; say so instead of faking one.
- Descriptions that are too modest under-trigger; Claude only consults a skill for tasks it cannot easily do alone, so make test queries substantial.
- Do not tune a skill only to its three test prompts; the aim is behaviour on unseen prompts.
- Re-check the upstream folder before relying on a script flag; the repo changes often.
