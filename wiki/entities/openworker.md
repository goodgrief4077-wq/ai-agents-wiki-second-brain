---
title: OpenWorker
type: tool
aliases:
  - andrewyng/openworker
sources:
  - 26-10-27-1030-openworker @ README
  - 26-10-27-1030-openworker-releases @ releases
  - 26-10-27-1031-openworker-openshell @ What you need
updated: 2026-10-27T10:29:00+09:00
status: draft
tool_version: 0.3.1
---
OpenWorker is an open-source, local-first desktop "AI coworker" that works across your files, terminal and connected apps and returns finished deliverables, with approval gating and an audit trail built into its runtime. It is in open beta.

## What it does
The README describes a native desktop shell over a local Python agent server built on aisuite, with 25+ connectors (GitHub, Slack, Jira, Notion, Linear and others), MCP support, scheduled automations, and bring-your-own-key access to many model providers or fully local models through Ollama and similar runtimes. Security-focused specialist coworkers (code review with scanners such as semgrep, cloud posture, incident triage) ship first, with everyday-work coworkers alongside.

Its governance model has four tiers: human-only hard floors that no auto-approve mode lowers, approvals that can graduate into standing rules, an audit trail recording approval provenance, and an optional sandbox for the commands an agent runs. Unattended runs park their approval requests rather than self-approving. The README states reviewer-model verdicts are judgments, not guarantees.

The sandbox page describes one OpenShell container per agent holding only the session's folders, with a network allow list and no keys inside, while the agent loop, keys and connectors stay outside.

## Limits
- The README lists downloads for macOS (Apple Silicon) and Windows only; on Linux it is run from source and needs Python, Node and the Rust toolchain. The GUI folder contains a `src-tauri` directory, so the shell looks like Tauri, not Electron (a secondary summary called it Electron; the repository tree does not).
- The sandbox requires Docker or Podman plus OpenShell 0.1.2. The OpenWorker sandbox page does not mention LXC or Incus, so LXC is not a documented backend. unsourced: whether OpenShell itself can run on an LXC runtime.
- Connector OAuth goes through a small cloud broker service; manual API keys avoid it.
- Smoke test not run: this page rests on the repository text, not on running the app.
- Beta, 30 commits at capture, releases v0.3.0 (2026-09-30) and v0.3.1 (2026-10-05).

## Using LXC or Incus with it (own analysis, unsourced)
- Option A, outer box: run the whole OpenWorker server inside an unprivileged LXC container, so a compromise stays off the host. The per-agent OpenShell wall is then missing unless Docker or Podman also runs inside that container, which needs nesting enabled.
- Option B, native: keep Docker or Podman on the host for OpenShell and use LXC only for other tools. Rootless Podman avoids adding the user to the `docker` group.
- For a disposable trial, a throwaway Incus or LXC container plus a local Ollama model keeps cost and data exposure at zero.

## Suggested system additions (own analysis, unsourced)
- Rootless Podman if only Docker is present and the user cannot reach its socket.
- Incus (or LXC) for disposable smoke-test containers, one per evaluated tool.
- A local model runtime (Ollama) already pulled, so trials need no key.
- A recorded approval and audit habit: if adopted, enable the sandbox first and keep connectors on read-only scopes until the trial passes.

## Disagreements
- [CONFLICT] A pasted secondary summary says the shell is Electron; the repository contains `src-tauri` and the README mentions the Rust toolchain (2026-10-27 tree listing, unsourced as a raw record).
