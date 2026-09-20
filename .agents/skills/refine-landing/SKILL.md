---
name: refine-landing
description: Refine an existing demo repository after client discovery using client-brief.json. Use only for post-discovery refinement; preserve good existing work and research gaps only.
---

Follow refinement mode.

1. Read `DISCOVERY_INPUT_CONTRACT.md`, `REFINEMENT_CONTRACT.md`, and the discovery JSON.
2. Delegate the initial repo audit to `repo_explorer`; keep its raw exploration out of the main thread.
3. Main agent writes `DEMO_AUDIT.md` from the explorer summary and discovery evidence.
4. Classify each question as resolved, unresolved, or contradicted.
5. Use `market_researcher` only for unresolved/contradicted market questions.
6. Use `visual_researcher` only if the post-discovery visual direction is still unresolved.
7. Main agent writes `DESIGN_DIRECTION.md` and `REFINEMENT_PLAN.md`.
8. Apply the asset policy in `.agents/skills/landing-assets/SKILL.md`.
9. Keep one writer: the main agent edits the existing repo. No parallel code-writing agents.
10. Load copy/design/SEO skills only for their phase.
11. Ask `reviewer` for a final read-only release review, then fix only concrete findings.

Do not repeat reliable research and do not regenerate the site from scratch without a documented reason.
