# Agent Efficiency Harness

Optimize for output quality per token, not maximum agent activity.

## 1. Orchestration

Main agent owns:
- task/mode resolution
- research synthesis
- design direction
- copy decisions
- implementation
- final fixes

Use subagents only when their isolated work would otherwise pollute the main context.

Default custom agents:
- `market_researcher` — Luna/medium, read-only
- `repo_explorer` — Luna/medium, read-only
- `visual_researcher` — Terra/medium, read-only, conditional
- `reviewer` — Terra/high, read-only, final gate

Do not spawn all agents automatically.

Maximum configured concurrency is 3. Prefer 1-2 useful subagents over a swarm.

Never use parallel code-writing agents for a normal site.

## 2. Model routing

Use the strongest model/main session for ambiguous multi-step synthesis and implementation.

Use Luna for:
- repo mapping
- extraction
- classification
- structured summaries
- narrow repetitive checks

Use Terra for:
- visual reference analysis
- nuanced review
- higher-risk validation

Use high reasoning only for final review or genuinely difficult ambiguity.

Do not use expensive reasoning for deterministic extraction.

## 3. Progressive disclosure

Root `AGENTS.md` is routing only.

Workflow details belong in skills because Codex loads full skill instructions only when selected.

Do not manually preload:
- design skill
- copy skill
- SEO skill
- all industry packs
- both generation/refinement contracts

Read only the selected industry and active workflow.

## 4. Asset budget

Default generated-asset budget: zero.

Use `landing-assets`.

Do not burn a run generating custom imagery, logos, illustrations, SVG scenes, textures, icon sets, or video for a first-contact demo.

Prefer existing/client/public temporary assets, CSS/typography, or explicit asset slots.

## 5. Research token discipline

- targeted searches, not broad browsing
- concise findings, not copied pages
- 1 positioning sentence + max 5-8 useful observations per reference
- stop when patterns repeat
- refinement mode researches gaps only
- subagents return distilled summaries only

## 6. Default frontend stack

For a normal institutional/business site, default to:

- Vite
- vanilla TypeScript
- semantic HTML
- plain CSS or a very small utility layer only if it reduces complexity
- static output
- Bun
- Cloudflare Pages
- no React by default

Framework escalation:

1. **Vanilla + Vite** — default for 1-5 mostly static pages.
2. **Astro** — use when multiple static routes, shared layouts, collections, or content reuse materially improve maintainability.
3. **Next.js / full app framework** — exception only for real runtime/app requirements.

SEO is not a reason to choose Next.js. Static HTML with correct metadata, structured content, robots/sitemap, canonical URLs, and crawlable links is sufficient for these sites.

Do not choose a framework because the agent is more familiar with it.

Normal small site:
- routing determined by SITE_STRATEGY.md
- single-page only when content fits without narrative compression
- multi-page allowed when distinct visitor intents/content domains justify it
- no arbitrary page-count target
- roughly 5-12 project-specific components
- 0 state libraries
- 0 UI frameworks
- 0 data-fetching libraries
- 0 context providers unless required
- 0 backend/database/auth unless requested
- 0 animation libraries unless design direction justifies one

## 7. Component rule

Extract a component only when it:
- is reused
- owns a substantial semantic section
- isolates real client behavior
- materially improves readability

No ceremony wrappers or speculative design systems.

## 8. Client JS

Default static HTML with minimal browser JavaScript.

Add JavaScript only for actual browser interaction.

Prefer CSS for hover, focus, responsive layout, and simple transitions.

## 9. Dependencies

Every dependency must provide something the browser platform, Vite, HTML, TypeScript, or CSS cannot provide simply enough.

If the justification is weak, do not install it.

## 10. Tests

For a mostly static landing:
- lint
- TypeScript
- production build
- responsive visual check
- keyboard/accessibility check
- links/form behavior

Do not build a large unit-test suite for static markup.

## 11. Deployment token budget

Default deployment-action budget: zero.

The harness ends after:
- local repository is complete
- local/static build passes
- required files exist
- remote/deployment settings are documented for the human operator

Do not spend tokens on:
- creating a GitHub repository
- configuring git remotes
- pushing commits
- GitHub CLI publication
- Cloudflare dashboard/browser navigation
- Wrangler deployment
- authentication
- DNS
- polling deployment state
- opening the deployed site for verification

These are human/manual steps unless explicitly requested.

## 12. Stop rules

Before adding a file, dependency, abstraction, agent, research source, or generated asset, ask whether it resolves a current requirement.

If not, stop.
