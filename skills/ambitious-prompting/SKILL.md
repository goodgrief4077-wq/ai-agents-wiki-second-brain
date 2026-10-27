---
name: ambitious-prompting
description: Use when a request looks like it could be done at a higher level, when the user says "be more ambitious", "go deeper", "think bigger", or hands over a task that only fills in a template or repeats a routine. Reframes the task by altitude (outcome, not task), depth (expert methods, raw data, outside judge) and range (methods from other fields), then rewrites the prompt. Do not use for small, well-specified edits where the literal task is what is wanted.
license: unknown (summary of a public blog post, nothing copied)
metadata:
  version: "1.0"
  updated: "2026-10-27"
  source: "felixrieseberg.com, How to be more ambitious: a tutorial for humans with models, 13 October 2026; wiki page ambitious-prompting"
---

# Ambitious prompting

Before doing a task literally, check whether a more ambitious framing would serve the user better. Offer the framing and let the user pick; never silently widen scope. Method summary and sources: wiki page `ambitious-prompting`.

## Steps
1. **Altitude.** Ask: what outcome is this task for, and what happens next? Offer to work toward the outcome (for example keep an app crash-free, not fix one crash). Works best when a real end result exists; skip for purely creative work.
2. **Gather inputs.** Ask for as much raw data as exists, then answer: what changed, why, what to do about it.
3. **Decisions.** Name the few most urgent decisions and give for and against arguments for each.
4. **Better process.** If the task is a routine (a report, a review), propose a better process, test it on past data, and suggest running it beside the old one.
5. **Depth.** Say what a top professional would do that was not asked for, which raw material they would start from, which tools and methods they would use (databases and statistics, not summary tables), and what outside check would show the result is right.
6. **Stretch the goal.** If the target looks safe, propose a much harder one and say it is solvable.
7. **Challenge beliefs.** Treat the user's assumptions as hypotheses and try to reproduce them from raw data; look for blind spots and test them on data not used to find them.
8. **Outside judge.** Prefer a tool you can run (tests, a benchmark, a held-out dataset) over grading your own work.
9. **Range.** Rewrite the deliverable as verbs (what it must get people to do), list the fields whose methods help, add an adversarial reviewer, and borrow what those experts do. Do not role-play a persona.
10. **Access check.** Confirm you can install tools and reach the data (files, connectors). If not, say what is missing before promising more.
11. **Rewrite the prompt** with the chosen framing, show it to the user, and run it only after they agree.

## Safety
- Widening scope can cost time, money and access. Ask before spending, installing or touching data outside the original request.
- Stop at the user's decision points; ambition is a proposal, not permission.
