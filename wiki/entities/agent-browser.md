---
title: agent-browser
type: tool
sources:
  - 26-10-24-1345-agent-browser @ README
  - 26-10-24-1345-agent-browser-releases @ releases
  - 26-10-27-1138-wiki-pr52-page-tiers @ description
updated: 2026-10-27T11:40:00+09:00
status: draft
tier: volatile
review_by: 2027-01-25
tool_version: 0.39.2
---
agent-browser is a browser automation command-line tool from Vercel Labs, built for AI agents to drive a real Chrome or Chromium browser.

## What it does
The README describes a native Rust binary that controls Chrome over the Chrome DevTools Protocol. By default it uses Chrome for Testing, and it detects existing Chrome, Brave, Playwright or Puppeteer installs; its background daemon needs neither Playwright nor Node.js. The main workflow is an accessibility-tree snapshot that gives each interactive element a short ref, which later commands such as click and fill act on. Install routes are a global package from the npm registry, Homebrew or Cargo, or a source build that needs Node.js 24+, pnpm 11+ and Rust. The README treats anything a page provides through WebMCP (tool names, descriptions, schemas, results) as untrusted data.

## Limits
Version taken from the GitHub releases page on 2026-10-24. This page covers the repository README only, not the separate docs site or the usage guides bundled with the package.

## Disagreements
None found.
