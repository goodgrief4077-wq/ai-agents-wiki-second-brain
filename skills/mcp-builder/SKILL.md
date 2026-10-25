---
name: mcp-builder
description: Use when the user says "build an MCP server", "wrap this API as MCP tools", "write MCP tools in TypeScript or Python", or "evaluate my MCP server", or asks how Anthropic's mcp-builder skill works. Maps its four phases (research, implement, review and test, evaluations) and lists install, safety and gotcha facts. Do not use to merely connect an existing MCP server to a client or to write a non-MCP integration.
license: Apache-2.0
metadata:
  version: "1.0"
  updated: "2026-10-25"
  source: "github.com/anthropics/skills skills/mcp-builder (SKILL.md, reference/, scripts/), main at commit dbd4588 (2026-10-09), Apache-2.0 per the folder's LICENSE.txt"
---

# mcp-builder

mcp-builder is Anthropic's guide skill for building a Model Context Protocol (MCP) server that lets an agent use an outside service through well-designed tools. It is Apache-2.0 licensed (the folder carries its own LICENSE.txt). Its test of quality is practical: can an agent finish real tasks with the tools. This note is a map, not a copy; read the upstream skill and its reference files before first use.

## Four phases

| Phase | What to do |
|---|---|
| 1 Research and plan | Learn current MCP design habits, read the protocol docs (the spec site offers markdown pages), read the SDK README, then list the service's endpoints, auth and data models and rank operations by how common they are |
| 2 Implement | Set up the project, build shared plumbing (API client, errors, pagination, formatting), then each tool with a typed input schema, an output schema where possible, a short description and behaviour hints |
| 3 Review and test | Remove duplication, keep error handling and types consistent, build, and try the server in the MCP Inspector |
| 4 Evaluate | Write ten hard, realistic read-only questions with single checkable answers, solve each yourself, store them in an XML question-and-answer file |

## Design points upstream stresses
- Prefer broad API coverage when unsure; add workflow tools only where a task clearly needs one.
- Consistent action-oriented tool names with a shared service prefix.
- Return focused data, support filtering and pagination, and keep descriptions concise.
- Error messages should tell the agent what to try next.
- Mark each tool read-only, destructive, idempotent or open-world through the annotation hints.
- Recommended stack: TypeScript with the official SDK; streamable HTTP with stateless JSON for remote servers, stdio for local ones. Python with FastMCP is the supported alternative.

## What is in the folder
- `reference/`: best practices, a TypeScript guide, a Python guide and an evaluation guide. Load them per phase, not all at once.
- `scripts/`: an evaluation runner, a connection helper, an example evaluation file and a requirements list.

## Install
The README of anthropics/skills describes adding the repo as a plugin marketplace in Claude Code (`/plugin marketplace add anthropics/skills`) and then choosing a plugin set. Read the plugin contents first. Check the README for which set lists mcp-builder; do not assume the document set does.

## Privacy and safety
- The generated server will hold the target service's credentials. Keep tokens in environment variables, never in the repo, and scope them to the least access needed.
- Evaluation questions must use read-only operations so a run cannot change real data.
- The eval runner calls a model with your server's output; do not point it at data you cannot share.

## Gotchas
- Fetching SDK and spec pages live is part of the method; they change, so trust them over memory.
- Questions whose answers drift over time make bad evaluations; choose stable facts.
- A server that only mirrors endpoints one to one can still fail agents; test with the evaluation, not just the build.
- Re-check the upstream folder before relying on a flag; the repo changes often.
