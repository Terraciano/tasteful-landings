---
name: generate-landing
description: Generate a first-contact demo business/brand site in a new local repository from public information. Institutional is the default site type; campaign landing behavior is opt-in.
---

Follow generate mode.

1. Run `site-strategy` first. Default to `institutional` unless the brief explicitly calls for a campaign landing. Create `research/SITE_STRATEGY.md`.
2. Read `PRINCIPLES.md`, `GENERATION_CONTRACT.md`, `RESEARCH_PROTOCOL.md`, and the matching industry `BRIEF.md` / `RESEARCH_PLAYBOOK.md`.
3. If the prospect already has a first-party website, run `extract-brand-baseline` before competitor or visual research and create `research/BRAND_BASELINE.md`.
4. If the prospect has meaningful first-party copy, run `extract-copy-baseline` and create `research/COPY_BASELINE.md`.
5. Use `market_researcher` for category language, direct competitors, trust signals, and search intent.
6. Spawn `visual_researcher` only when visual direction remains ambiguous after brand + market research. Do not spawn it by default.
7. Synthesize `MARKET.md`, `COMPETITORS.md`, `REFERENCES.md`, and `DESIGN_DIRECTION.md` in the main thread.
8. In `DESIGN_DIRECTION.md`, explicitly reconcile every proposed palette/type/shape decision with `BRAND_BASELINE.md` when that file exists.
9. Apply the asset policy in `.agents/skills/landing-assets/SKILL.md`.
10. Default implementation stack is Vite + vanilla TypeScript + CSS, producing static HTML for Cloudflare Pages.
11. Use Astro only when multiple static routes, repeated layouts/content, or content structure materially benefits from it.
12. Use Next.js only when the brief truly needs app/runtime behavior that static Vite/Astro cannot satisfy. Framework familiarity is not a justification.
13. Load `design-taste-frontend` only for design/implementation.
14. Before copywriting, read `SITE_STRATEGY.md` and `COPY_BASELINE.md` when present.
15. For institutional sites, use copywriting to improve clarity/structure without erasing narrative. Do not blindly apply campaign formulas such as one CTA, pain/solution, or aggressive compression.
16. Load `copywriting` only when writing/reviewing final copy.
17. Keep one writer: the main agent owns implementation. Do not delegate code writing in parallel.
18. Load `seo-audit` only at release.
19. Run the minimum release checks from the generation contract.

Stop research when the protocol stop condition is met. Do not keep browsing to make research documents longer.
