---
name: refine-landing
description: Refine an existing demo site after client discovery using client-brief.json. Preserve institutional narrative/identity and research gaps only.
---

Follow refinement mode.

1. Read `DISCOVERY_INPUT_CONTRACT.md`, `REFINEMENT_CONTRACT.md`, and the discovery JSON.
2. Resolve/confirm site type and routing with `site-strategy`. Discovery may change the initial one-page hypothesis.
3. Preserve or update `COPY_BASELINE.md` when the real business has meaningful existing narrative.
4. Delegate the initial repo audit to `repo_explorer`; keep its raw exploration out of the main thread.
5. Main agent writes `DEMO_AUDIT.md` from the explorer summary and discovery evidence.
6. Classify each question as resolved, unresolved, or contradicted.
7. Use `market_researcher` only for unresolved/contradicted market questions.
8. Use `visual_researcher` only if the post-discovery visual direction is still unresolved.
9. Main agent writes `DESIGN_DIRECTION.md` and `REFINEMENT_PLAN.md`.
10. Apply the asset policy in `.agents/skills/landing-assets/SKILL.md`.
11. Keep one writer: the main agent edits the existing repo. No parallel code-writing agents.
12. Load copy/design/SEO skills only for their phase. For institutional sites, copy refinement must preserve narrative jobs and brand language.
13. Ask `reviewer` for a final read-only release review, then fix only concrete findings.

Do not repeat reliable research and do not regenerate the site from scratch without a documented reason.
