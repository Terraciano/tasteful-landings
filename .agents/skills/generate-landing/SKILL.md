---
name: generate-landing
description: Generate a first-contact demo landing in a new repository from public information. Use only when there is no existing demo repo and the task is to create the initial sales hypothesis.
---

Follow generate mode.

1. Read `PRINCIPLES.md`, `GENERATION_CONTRACT.md`, `RESEARCH_PROTOCOL.md`, and the matching industry `BRIEF.md` / `RESEARCH_PLAYBOOK.md`.
2. Use `market_researcher` for category language, direct competitors, trust signals, and search intent.
3. Spawn `visual_researcher` only when visual direction remains ambiguous after market research. Do not spawn it by default.
4. Synthesize `MARKET.md`, `COMPETITORS.md`, `REFERENCES.md`, and `DESIGN_DIRECTION.md` in the main thread.
5. Apply the asset policy in `.agents/skills/landing-assets/SKILL.md`.
6. Load `design-taste-frontend` only for design/implementation.
7. Load `copywriting` only when writing/reviewing final copy.
8. Keep one writer: the main agent owns implementation. Do not delegate code writing in parallel.
9. Load `seo-audit` only at release.
10. Run the minimum release checks from the generation contract.

Stop research when the protocol stop condition is met. Do not keep browsing to make research documents longer.
