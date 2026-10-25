---
name: web-quality-skills
description: Use when the user says "use web-quality-skills", "audit my site", "accessibility audit", "WCAG review", "fix Core Web Vitals", or wants a measurement-first web quality pass (accessibility, performance, SEO, best practices) from the addyosmani/web-quality-skills repo. Maps each concern to the upstream skill and lists the evidence order, install and safety facts. Do not use as proof of WCAG conformance, as a replacement for manual testing with real assistive technology, or for non-web projects.
license: MIT
metadata:
  version: "1.0"
  updated: "2026-10-25"
  source: "github.com/addyosmani/web-quality-skills README and skill folders, main at commit afa8da9 (2026-08-24), skills version 2.0 series, MIT (LICENSE file in repo root)"
---

# web-quality-skills

An MIT-licensed, stack-agnostic pack of six Markdown skills by Addy Osmani for auditing and improving web pages. It is unofficial and measurement-first: collect live evidence (Lighthouse, traces, accessibility tree) before reading code, and keep measured failures separate from guesses made from source alone. Third-party code. This skill is a map and a safety note, not a copy; read the upstream skill before first use.

## Pick the skill by concern

| Concern | Upstream skill | What it does (own words) |
|---|---|---|
| Whole-page review | `web-quality-audit` | Orchestrates the others; sets audit scope, routes to the best available tool, reports verified versus unverified findings; ships a static analyzer script as a smoke test |
| Accessibility | `accessibility` | WCAG 2.2 guidance organised by the four principles (perceivable, operable, understandable, robust), with a testing checklist and issues ranked by impact |
| Speed | `performance` | Field and lab measurement, loading and runtime fixes, starting budgets |
| Vitals | `core-web-vitals` | Diagnosis of LCP, INP and CLS against the published good thresholds at the 75th percentile |
| Search | `seo` | Crawlability, metadata, structured data |
| Hygiene | `best-practices` | HTTPS and security headers, modern APIs, console cleanliness, compatibility |

## Evidence order (the core idea)
1. Define the target: representative URLs, key user journeys, public versus signed-in, mobile and desktop.
2. Run an automated audit on the rendered page (Lighthouse, or axe) and use failed nodes to find the component, instead of grepping the whole repo.
3. Inspect the accessibility tree (names, roles, states, landmarks, headings) and drive the affected flow with the keyboard alone.
4. For speed, prefer field data (CrUX or the site's own real-user data) for impact and a browser trace for cause; a lab run is one observation, not field data.
5. Fix the source, re-run the same checks, and report what is verified and what still needs human or field validation.
6. If the page cannot run, say findings are hypotheses from source.

## Accessibility notes
- WCAG 2.2 additions the upstream skill covers: focus not obscured, minimum target size, dragging alternatives, consistent help, redundant entry and accessible authentication.
- Automated tools find only a subset of barriers. A perfect score is not conformance; a low score does not replace issue-level evidence. Finish with keyboard and screen-reader passes.
- Upstream treats scores as regression guardrails, not goals; compare runs made with the same tool version.

## Install
1. Read the README install section and the skill you want before installing.
2. Any agent, as the README states: `npx skills add addyosmani/web-quality-skills`.
3. Claude Code plugin: `/plugin marketplace add addyosmani/web-quality-skills`, then `/plugin install web-quality-skills@addy-web-quality-skills`; skills are then namespaced.
4. Manual: copy the repo's `skills/` folders into `~/.claude/skills/`. Codex and Gemini CLI have their own commands in the README and its docs folder.
5. Optional: Chrome DevTools MCP gives live Lighthouse audits, traces and accessibility snapshots; without it the skills fall back to Lighthouse CLI, PageSpeed tools and manual checks.
6. Verify by invoking one skill by name; it must be recognised.

## Privacy and safety
- Plain Markdown plus one shell script in `web-quality-audit`; read the script before running it.
- No telemetry is described in the README. Audits of live pages send requests to those pages and, for hosted tools, the URL to a third party; do not audit private or signed-in pages with a hosted tool.
- A navigation-mode audit reloads the page and can lose signed-in or unsaved state; use snapshot mode there.

## Gotchas
- Lighthouse and its audit IDs change between major versions; upstream says to follow current insight names, not removed ones.
- The performance budgets in the README are starting points, not universal limits; set them from your own devices and users.
- A Core Web Vitals pass does not promise a search ranking change.
- Skill content and versions move; re-check upstream descriptions before relying on one.
