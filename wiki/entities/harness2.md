---
title: Harness2
type: tool
aliases:
  - Harness²
  - google-research/harness2
sources:
  - 26-10-26-1414-harness2 @ README
  - 26-10-26-1414-harness2-releases @ releases
updated: 2026-10-26T14:15:00+09:00
status: draft
tool_version: unreleased
---
Harness2 (written Harness² by its authors) is a Google Research framework, under the Apache-2.0 licence, for improving the harness around an AI model without changing the model's weights. It works with the OpenCode and [[codex]] executors.

## What it does
The README defines a harness as the system around a model (prompts, tools, memory, skills, orchestration) and describes two levels of recursion. Task-level recursion refines the harness for the current task by proposing edits, probing their effects on the same task, and composing a refined harness. Harnessing-level recursion keeps a persistent improvement harness that learns from adopted harnesses and evidence from each task. It exposes eight editable components: system prompt, guardrails, memory, tool guidance, subagents, skills, scripts and plugins. The README reports gains of up to 11.5 points on WorkBuddy-Bench, 4.5 on JobBench and 11.8 percentage points on LAB, for GLM-5 and Gemini 3.5 Flash; these are the authors' claims and were not verified here.

## Limits
The repository shows no releases as of 2026-10-26, so the version is `unreleased`. It targets Linux, Python 3.12 and uv. Model-backed runs need the Google Cloud CLI and Vertex AI model settings and incur API costs; some benchmarks need Docker, Pandoc and Poppler. A credential-free local demo is described. Popularity figures in secondary sources vary and are not recorded here.

## Disagreements
None found.
