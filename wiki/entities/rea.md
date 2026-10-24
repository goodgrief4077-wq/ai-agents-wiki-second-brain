---
title: REA (Reverse Engineer Anything)
type: tool
sources:
  - 26-10-24-1345-rea @ README
  - 26-10-24-1345-rea-releases @ releases
updated: 2026-10-24T13:49:07+09:00
status: draft
tool_version: 6.7.0
---
REA is an MCP server and command-line tool that lets a coding agent reverse engineer binaries, applications and runtime behaviour and get findings back with evidence.

## What it does
The README presents one MCP server, with a CLI that runs the same workflows. An agent calls it to inspect a target and trace code, then uses the evidence-backed findings to explain behaviour or build a similar feature. An interactive setup command registers the server and matching workflow instructions with agents including Claude Code, Codex, Cursor and Gemini CLI, and backs up existing configuration first. A CLI command analyses an extracted JavaScript or Electron app folder or ASAR archive and returns modules, imports and Electron boundaries. Native binary analysis needs Hopper, Ghidra or IDA. Other targets, such as Go binaries, GPU code objects, model files, Unity IL2CPP metadata and Godot packs, use built-in static inspection. It needs a recent Node.js 22, 24 or 26 release.

The README warns that only the morluto/rea repository, the rea.tools site and the rea-agents package are official, and that a similar repository name or copied README is not proof of an official download.

## Limits
Version taken from the GitHub releases page on 2026-10-24. Releases are very frequent, so the version goes stale fast. This page covers the README only, not the guides on rea.tools. Repository popularity figures are left out on purpose because they changed sharply within days; check them live.

## Disagreements
None found.
