---
name: wshobson-agents
description: Use when the user says "use wshobson agents", "prompt engineering patterns", "improve this prompt", "build an LLM agent with LangGraph", "evaluate my LLM app", or wants the LLM application plugin (prompting, agents, RAG, evaluation) from the wshobson/agents plugin marketplace. Maps each task to the upstream skill and lists install, safety and gotcha facts. Do not use as a replacement for measuring a prompt on your own test inputs, or for provider-specific API questions that the provider docs answer.
license: MIT
metadata:
  version: "1.0"
  updated: "2026-10-25"
  source: "github.com/wshobson/agents plugins/llm-application-dev (skills, agents, commands) and README, main at commit 0874a27 (2026-10-17), plugin version 2.0.6, MIT per the root LICENSE file"
---

# wshobson-agents (llm-application-dev plugin)

wshobson/agents is a large MIT-licensed plugin marketplace of agents, skills and commands (about 90 local plugins). For agent development and prompt patterns the relevant one is the `llm-application-dev` plugin: eight skills, three agents and three commands. Third-party code. This note is a map and a safety note, not a copy; read the upstream skill before first use.

## Pick the skill by task

| Task | Skill | What it covers (own words) |
|---|---|---|
| Write or fix a prompt | `prompt-engineering-patterns` | Few-shot example selection, chain-of-thought, structured output with schemas, templates, system prompts, iterative optimisation; deeper guides in its `references/` and a template library in `assets/` |
| Build an agent | `langchain-architecture` | LangChain 1.x and LangGraph agents, memory and tool integration |
| Know if it works | `llm-evaluation` | Automated metrics, human feedback, A/B tests and benchmarks |
| Ground answers in documents | `rag-implementation` | Retrieval-augmented generation with vector stores |
| Retrieval quality | `embedding-strategies`, `hybrid-search-implementation`, `similarity-search-patterns`, `vector-index-tuning` | Embedding choice and chunking, vector plus keyword search, nearest-neighbour queries, index tuning for latency, recall and memory |

The plugin also ships agents (`ai-engineer`, `prompt-engineer`, `vector-database-engineer`) and commands (`ai-assistant`, `langchain-agent`, `prompt-optimize`). The same marketplace has neighbouring plugins worth a look for multi-agent work: `agent-teams` (team composition, task coordination, parallel debugging and review patterns), `agent-orchestration` and `llm-finetuning`.

## Prompt patterns in brief (from the prompt skill)
- Be specific; show examples rather than describe; fix a consistent example format.
- Choose few-shot examples by similarity, diversity, difficulty or past errors, within the context budget.
- Ask for step-by-step reasoning where accuracy matters; sample several paths and compare for self-consistency.
- Enforce an output schema and handle malformed output.
- Treat a prompt as code: baseline, change one thing, test on varied inputs, version it, keep a rollback.
- Common fixes in order: add structure, add examples, add constraints, add a verification step.

## Install
1. Read the README's install section; pick ONE route per agent.
2. Claude Code, as the README states: `/plugin marketplace add wshobson/agents`, then `/plugin install llm-application-dev@claude-code-workflows`.
3. One skill only, as the README states: `npx skills add wshobson/agents --skill prompt-engineering-patterns`, or `gh skill install wshobson/agents prompt-engineering-patterns` (needs a current GitHub CLI). Pick the coding tool when prompted.
4. Other harnesses (Codex, Cursor, OpenCode, Copilot and more) have their own routes in the README and its harness doc.
5. Verify by asking for a prompt review and checking that the skill is named in the answer.

## Privacy and safety
- Skills are Markdown; read them first. The prompt skill also bundles a Python helper script; read it before running it.
- Example code calls hosted model APIs and needs your own key. Keep keys in environment variables, never in the repo.
- Prompts and test data you send to an API leave your machine; do not use data you cannot share.

## Gotchas
- Install the plugin you need, not the whole marketplace; many plugins add many agents and slow routing.
- Example code pins model names and library versions that go stale; check current ones before copying.
- The prompt skill's body is short and sends details to `references/details.md`; read that file for worked examples.
- Techniques such as "think step by step" help less on models that already reason by default; test before keeping them.
- The repo changes often. Re-check the upstream skill description before relying on a name or flag.
