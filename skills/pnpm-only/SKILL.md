---
name: pnpm-only
description: Use when setting up a machine so coding agents install JavaScript packages only with pnpm, when an agent reaches for npm or npx, or when the user says "pnpm only", "get npm out", "block npm". Sets pnpm's supply-chain guards, removes npm and npx from the Node install, switches mise's npm backend to pnpm, and adds a Claude Code hook that refuses npm/npx. Do not use for projects that must ship an npm lockfile.
---

# pnpm-only for coding agents

Goal: every agent on the machine (Claude Code, opencode, pi, Codex and others) uses pnpm with release-age and trust checks, and none can fall back to npm or npx.

## Steps
1. **Install pnpm** through your version manager (for mise: `mise use -g pnpm@latest`), not through npm.
2. **Guards** in `~/.config/pnpm/config.yaml` (use an age that suits you; 10080 minutes is 7 days):
   ```yaml
   minimumReleaseAge: 10080
   trustPolicy: no-downgrade
   blockExoticSubdeps: true
   strictDepBuilds: true
   ```
   Check: `pnpm config get minimumReleaseAge`. Never weaken a guard to make one install pass; exclude only the exact package and version, and only with the user's OK.
3. **mise npm backend:** `mise settings set npm.package_manager pnpm`, so tools mise installs from npm (for example opencode) also go through pnpm.
4. **Remove npm and npx from Node.** They ship as links next to `node`: `ls -la "$(mise where node)/bin"`. Move `npm` and `npx` to the trash (not a hard delete), then `mise reshim` and `hash -r`. Check: `npm -v` says command not found, `pnpm -v` works. This is what keeps non-Claude agents off npm. Tell the user before doing it, and check nothing they run depends on npm first.
5. **Claude Code hook:** save [block-npm-hook.md](block-npm-hook.md) as `~/.claude/hooks/block-npm.sh`, make it executable, and add it under `hooks.PreToolUse` in `~/.claude/settings.json` with matcher `Bash`. Back up settings.json first. Test it with the cases in that file before relying on it.
6. **Report:** what changed, how each part was checked, and the limits below.

## Limits
- Reinstalling or upgrading Node through the version manager brings npm and npx back; repeat step 4 after a Node install.
- The hook covers Claude Code only. Other agents are held only by step 4.
- Tool READMEs often say `npx <tool>` or `npm i -g <tool>`; translate to `pnpm dlx <tool>` or `pnpm add -g <tool>`.

## Gotchas
- A hook that matches "npm" anywhere in the command also blocks commands that only mention it (commit messages, heredoc text, grep patterns). Match command positions only; the hook file does this.
- pnpm's global bin folder must be on PATH (`pnpm setup` adds `PNPM_HOME`); open a new shell to pick it up.

## Checklist
- [ ] pnpm installed without npm, guards set and read back
- [ ] mise npm.package_manager is pnpm (if mise is used)
- [ ] `npm -v` fails, `pnpm -v` works
- [ ] Hook installed, settings.json backed up, test cases pass
