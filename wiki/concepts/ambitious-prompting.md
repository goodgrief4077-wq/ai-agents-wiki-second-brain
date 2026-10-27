---
title: Ambitious prompting
type: method
aliases:
  - altitude depth range
  - being more ambitious with AI
sources:
  - 26-10-27-1007-felix-rieseberg-ambitious @ Altitude
  - 26-10-27-1007-felix-rieseberg-ambitious @ Depth
  - 26-10-27-1007-felix-rieseberg-ambitious @ Range
  - 26-10-27-1007-felix-rieseberg-ambitious @ We have been here before
updated: 2026-10-27T10:07:46+09:00
status: draft
---
A way to ask a model for more than the literal task, taught in one Claude engineer's blog post. It names four types of ambition: speed (the same work faster, treated as already well understood), altitude, depth and range. The post's advice is not tied to one model. Related: [[agent-workflow-patterns]], [[claude-code]], [[writing-effective-agent-skills]].

## When it applies
Any task where the first prompt that comes to mind only fills in a template or repeats last quarter's work: reports, reviews, analyses, recurring fixes, and creative or production work that benefits from several disciplines. The post says altitude fits goals with a real end outcome (a sign is that you would hold a meeting about it) and fits creative work less well.

## Steps
1. Altitude: restate the task as the outcome behind it, for example from fixing one crash to keeping an app crash-free. (src: 26-10-27-1007-felix-rieseberg-ambitious @ Altitude)
2. Give the model as much real data as you can, then ask what changed, why, and what to do about it. (src: 26-10-27-1007-felix-rieseberg-ambitious @ Altitude)
3. Ask it to pick the few most urgent decisions and argue for and against each direction. (src: 26-10-27-1007-felix-rieseberg-ambitious @ Altitude)
4. Ask it to design a better process than the one you use, test it on your own history, and run it beside the old one for a period. (src: 26-10-27-1007-felix-rieseberg-ambitious @ Altitude)
5. For a durable workflow, first give the model the access it needs to fetch inputs, map versions to code and reproduce and verify results itself. (src: 26-10-27-1007-felix-rieseberg-ambitious @ Altitude)
6. Depth: require the instruments professionals use, such as databases and statistical models, not summary tables. (src: 26-10-27-1007-felix-rieseberg-ambitious @ Depth)
7. Set a goal that looks unreasonable (the post's example is 200 ms instead of 5 s) and say it is solvable. (src: 26-10-27-1007-felix-rieseberg-ambitious @ Depth)
8. Give the model raw data and ask it to test your beliefs adversarially, then to look for blind spots and check them on unseen data. (src: 26-10-27-1007-felix-rieseberg-ambitious @ Depth)
9. Use an outside judge, ideally a tool the model can run, instead of asking the model to grade itself. (src: 26-10-27-1007-felix-rieseberg-ambitious @ Depth)
10. Optional prompt: ask for a deeper, not bigger, version; have the model name what a top professional would do, the rawest material, the methods and tools, and what outside the model and you would show the result is right. (src: 26-10-27-1007-felix-rieseberg-ambitious @ Depth)
11. Range: rewrite the deliverable as verbs (what it must get people to do), then list the fields that bring those skills. (src: 26-10-27-1007-felix-rieseberg-ambitious @ Range)
12. Assemble a crew of fields, including an adversarial red team, and ask for what those experts do, not for role-play. (src: 26-10-27-1007-felix-rieseberg-ambitious @ Range)
13. Give the model a computer that can install software and reach the relevant data, for example through MCP connectors. (src: 26-10-27-1007-felix-rieseberg-ambitious @ Range)
14. Mindset: specific hard goals beat "do your best", and the post cites examples of people doing hard things once they believed them possible or saw them done. (src: 26-10-27-1007-felix-rieseberg-ambitious @ We have been here before)

## Disagreements
None recorded. The post is one author's opinion; the research claims (goal-setting studies, self-efficacy) are unsourced beyond the post itself.
