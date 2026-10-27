---
title: huggingface_hub
type: tool
sources:
  - 2026-10-11-hugging-face-hub @ page
  - 2026-10-12-hugging-face-hub-releases @ releases
  - 26-10-27-1138-wiki-pr52-page-tiers @ description
updated: 2026-10-27T11:40:00+09:00
status: draft
tier: volatile
review_by: 2027-01-25
tool_version: v2.2.0
---
huggingface_hub is the official Python library and hf command-line tool for working with the Hugging Face Hub.

## What it does
The README describes huggingface_hub as the official CLI and Python client for the Hugging Face Hub, shipped in one package with the hf CLI and a Python library. Listed uses: download and upload files, manage repositories, run inference on deployed models, run jobs on Hugging Face infrastructure, search models, datasets and Spaces, and share model cards. The hf CLI adapts its output when run by an agent, and a skills command installs a CLI reference as an agent skill for Claude Code, Codex, Cursor, OpenCode, Pi and other skill-loading agents. The library installs with pip (an optional extra adds an MCP module) and authentication uses Hub tokens.

## Limits
Version taken from the GitHub releases page on 2026-10-12. This is the client library, not the Hub service itself. This page covers the repository front page and README only.

## Disagreements
None found.
