---
title: pnpm-only package policy for coding agents
type: method
sources:
  - 26-10-24-1347-pnpm-dependency-resolution-settings @ minimumReleaseAge
  - 26-10-24-1347-pnpm-dependency-resolution-settings @ trustPolicy
  - 26-10-24-1347-pnpm-dependency-resolution-settings @ blockExoticSubdeps
  - 26-10-24-1347-pnpm-build-settings @ strictDepBuilds
  - 26-10-24-1346-mise-settings @ npm.package_manager
  - 26-10-24-1346-claude-code-hooks @ Exit code 2 behavior per event
  - 26-10-27-1138-wiki-pr52-page-tiers @ description
updated: 2026-10-27T11:40:00+09:00
status: draft
tier: core
---
A way to make every JavaScript package that coding agents install go through pnpm, with its supply-chain guards switched on, so that no agent can fall back to npm or npx.

## When it applies
A machine where agents install or run JavaScript tools, and the owner wants one package manager with release-age and trust checks instead of whatever an agent reaches for first. Pairs with [[claude-code]] hooks when Claude Code is one of the agents.

## Steps
1. Hold back brand-new releases: set minimumReleaseAge (minutes) so a version is installable only after it has been public for that long, for transitive dependencies too. (src: 26-10-24-1347-pnpm-dependency-resolution-settings @ minimumReleaseAge)
2. Refuse trust downgrades: set trustPolicy to no-downgrade so an install fails when a release has weaker publish evidence than an earlier one. (src: 26-10-24-1347-pnpm-dependency-resolution-settings @ trustPolicy)
3. Keep blockExoticSubdeps on so only direct dependencies may come from git or tarball URLs. (src: 26-10-24-1347-pnpm-dependency-resolution-settings @ blockExoticSubdeps)
4. Keep strictDepBuilds on so unreviewed install scripts stop the install; allow builds per package only when needed. (src: 26-10-24-1347-pnpm-build-settings @ strictDepBuilds)
5. If tools come from mise's npm backend, set npm.package_manager to pnpm so mise itself installs them with pnpm. (src: 26-10-24-1346-mise-settings @ npm.package_manager)
6. For Claude Code, add a PreToolUse hook on the Bash tool that exits with code 2 when a command runs npm or npx; that blocks the call and shows the hook's message to the agent. (src: 26-10-24-1346-claude-code-hooks @ Exit code 2 behavior per event)

## Limits
Unsourced, from one Linux setup on 2026-10-24: a Node.js install from a version manager still ships npm and npx next to node, so removing those two links (and rebuilding the manager's shims) is what keeps agents other than Claude Code off npm; reinstalling Node brings them back. A hook that matches npm anywhere in the command text also blocks commands that only mention it (heredoc bodies, quoted grep patterns); match only command positions.

## Disagreements
None found.
