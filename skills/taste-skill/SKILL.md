---
name: taste-skill
description: Use when the user says "use taste skill", "design-taste-frontend", "make this page not look AI-made", "award-level landing page", or asks for art-directed web pages or dashboards with real photographs and a real-browser check from Leonxlnx/taste-skill. Maps the skill's run, scripts, install and safety facts. Do not use for quick CSS tweaks, for backend work, or on a machine without Node and a Chromium-family browser.
license: MIT
metadata:
  version: "1.0"
  updated: "2026-10-25"
  source: "github.com/Leonxlnx/taste-skill README, CHANGELOG and skills/taste-skill, main at commit 12af471 (2026-10-25), version series 2.1, MIT"
---

# taste-skill

taste-skill is an MIT-licensed anti-slop design skill. The repo now holds one skill, installed under the name `design-taste-frontend` (the folder is `skills/taste-skill`). It is third-party code with scripts; this note is a map and a safety note, not a copy. Read the upstream SKILL.md and scripts before first use.

## The run, in short

| Step | What happens |
|---|---|
| Brief | Agent reads the brief and project, lists what only this client has |
| Direction | A script deals three of twenty researched directions; the agent picks one |
| Idea | One sentence tying the client's own material to that direction |
| Build | Real pictures from open archives, credited; no stock-card kit |
| Gate | Scripts check the page in a real browser at three widths and fail it on "slop" |
| Look and fix | Agent views its own screenshots and fixes the worst problems, up to three rounds |
| Report | Summary of choices, credits and remaining issues |

Dashboards and app screens take a separate route (app styles, aligned figures, data-spent colour, phone layout). Upstream says a build takes about 30 to 45 minutes and a few hundred thousand tokens.

## Moved skills
Older skills (minimalist, brutalist, image-generation, brand kit and others) now live in separate repos by the same author; the README has the table. A redesign audit is part of this skill.

## Install
1. Requirements per the README: Node 22 or newer, an installed Chrome, Edge or Chromium. Check `node --version`.
2. Read the upstream `install.sh` and `skills/taste-skill/scripts/` first.
3. README command: `npx skills add https://github.com/Leonxlnx/taste-skill --skill "design-taste-frontend"`.
4. Claude Code plugin route from the README: `/plugin marketplace add Leonxlnx/taste-skill`, then `/plugin install taste-skill@taste-skill`; update with `/plugin update`.
5. Clone route: `./install.sh` symlinks the skill so a `git pull` updates it.
6. Re-running the install command upgrades an existing copy; the install name is stable.

## Privacy
- The README says the skill installs nothing and needs no API keys.
- The picture-finding script needs network access to open archives; with no network the skill falls back to drawn pictures and says so.
- Sponsor links and a desktop app are advertised in the README; they are not part of the skill.

## Gotchas
- Heavy: long runs and many tokens; not for small edits.
- It launches a real browser for checks; do not run it on a headless box without Chromium.
- Releases are frequent (several fixes land per week); re-read the changelog before trusting a flag.
- Overlaps with `frontend-design` and `ui-ux-pro-max`; pick one lead skill per build.
