---
title: Kindi
type: tool
aliases:
  - ahtx/kindi
sources:
  - 26-10-26-1414-kindi @ README
  - 26-10-26-1414-kindi-releases @ releases
updated: 2026-10-26T14:15:00+09:00
status: draft
tool_version: 0.2.0
---
Kindi is a custom inference engine, not a coding agent, for Prism ML's Ternary-Bonsai-2 language models on low-cost NVIDIA GPUs. Compare [[llama-cpp]] and [[ollama]].

## What it does
The README says it runs the 2B, 4B, 9B and 27B models, starting from a 1 GB Quadro K420, and version 0.2.0 adds the Quadro K1200 (including two cards in tensor parallel), GTX 1080, RTX 3080 and a CPU engine. It provides an OpenAI-compatible server so chat clients, scripts and coding agents can connect, and a one-command installer for Linux x86-64. The README states its default output is token-for-token identical to llama.cpp for the same model file, and shows the [[pi-coding-agent]] connected to it. Performance numbers (for example about 13x faster than llama.cpp on the K420) are the author's own claims and were not verified here.

## Limits
Version taken from the GitHub releases page on 2026-10-26. The project is young (6 commits at retrieval). It is licensed AGPL-3.0, and the repository also contains a separate commercial licence file. Linux x86-64 with NVIDIA drivers is the documented target. This page covers the front page and releases page only.

## Disagreements
None found.
