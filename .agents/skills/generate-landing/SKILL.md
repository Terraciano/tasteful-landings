---
name: generate-landing
description: Generate a first-contact demo landing in a new repository from public information. Use only when there is no existing demo repo and the task is to create the initial sales hypothesis.
---

Follow generate mode.

1. Read `PRINCIPLES.md`, `GENERATION_CONTRACT.md`, `RESEARCH_PROTOCOL.md`, and the matching industry `BRIEF.md` / `RESEARCH_PLAYBOOK.md`.
2. If the prospect already has a first-party website, run `extract-brand-baseline` before competitor or visual research and create `research/BRAND_BASELINE.md`.
3. Use `market_researcher` for category language, direct competitors, trust signals, and search intent.
4. Spawn `visual_researcher` only when visual direction remains ambiguous after brand + market research. Do not spawn it by default.
5. Synthesize `MARKET.md`, `COMPETITORS.md`, `REFERENCES.md`, and `DESIGN_DIRECTION.md` in the main thread.
6. In `DESIGN_DIRECTION.md`, explicitly reconcile every proposed palette/type/shape decision with `BRAND_BASELINE.md` when that file exists.
7. Apply the asset policy in `.agents/skills/landing-assets/SKILL.md`.
8. Default implementation stack is Vite + vanilla TypeScript + CSS, producing static HTML for Cloudflare Pages.
9. Use Astro only when multiple static routes, repeated layouts/content, or content structure materially benefits from it.
10. Use Next.js only when the brief truly needs app/runtime behavior that static Vite/Astro cannot satisfy. Framework familiarity is not a justification.
11. Load `design-taste-frontend` only for design/implementation.
12. Load `copywriting` only when writing/reviewing final copy.
13. Keep one writer: the main agent owns implementation. Do not delegate code writing in parallel.
14. Load `seo-audit` only at release.
15. Run the minimum release checks from the generation contract.

Stop research when the protocol stop condition is met. Do not keep browsing to make research documents longer.
