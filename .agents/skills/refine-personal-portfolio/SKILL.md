---
name: refine-personal-portfolio
description: Refine an existing personal portfolio/site so it preserves the person's real identity while making their work, credibility, and commercial offer easier to understand. Use for an existing personal site; do not turn it into a generic agency site.
---

# Refine personal portfolio

Use this workflow only when an existing personal website/repository is the target.

The site owner is the brand. Preserve authorship, personality, technical/creative identity, and any recognizable visual signature unless the operator explicitly asks to remove them.

## Objective

Improve the existing site so it can simultaneously:
- represent the person
- show what they make/do
- prove technical or professional credibility
- present selected commercial/client work
- make contact easy

Do not optimize it as a generic agency funnel.

## Workflow

1. Read `PRINCIPLES.md` and inspect the existing target repository.
2. Delegate repository mapping to `repo_explorer`. Focus on:
   - current information architecture
   - visual/interaction signature
   - distinctive code/creative elements
   - existing work/project data
   - navigation and mobile behavior
   - expensive or fragile interactive elements
   - what can be reused instead of rebuilt
3. Run `site-strategy` with `site type = personal-portfolio` and create `research/SITE_STRATEGY.md`.
4. Create `research/BRAND_BASELINE.md` from the existing site itself. Treat the person's current site, long-standing visual identity, and real public profiles/assets supplied by the operator as first-party brand evidence.
5. Create `research/COPY_BASELINE.md` from existing first-party copy when meaningful.
6. Main agent writes `research/DESIGN_DIRECTION.md`.
7. Main agent writes `REFINEMENT_PLAN.md` with the smallest coherent change set.
8. Implement in the existing repository. Keep one implementation writer.
9. Reuse existing visual/interactive systems when practical. Do not rebuild a technically interesting hero merely to make it more novel.
10. Load design/copy skills only for the phases where they are needed.
11. Ask `reviewer` for a final read-only release review and fix only concrete findings.
12. Run the repository's existing build/typecheck/lint commands as applicable.
13. Stop at a complete local repository. Do not create/change remotes, push, deploy, configure hosting/DNS, or inspect production unless explicitly requested.

## Personal-portfolio strategy rules

The default priority is:

identity → clarity → evidence → selected work → credibility → contact

The site may serve multiple audiences at once. Do not force a single marketing persona or a campaign-style one-CTA funnel.

Typical audiences may include:
- potential clients
- technical peers
- hiring/recruiting contacts
- collaborators
- people arriving from GitHub/LinkedIn/social profiles

## Commercial-work presentation

When commercial work is part of the goal:
- describe the offer in plain language
- prefer "specialist businesses", "high-value products and services", "institutional websites", or similarly accurate language when supported by the brief
- do not force "luxury" positioning onto the site or onto client businesses
- distinguish clearly between client work, work in progress, concepts, redesign studies, experiments, and open-source/technical projects
- never imply a concept or speculative redesign was paid client work
- never invent business outcomes, testimonials, revenue, conversion lifts, or client approval

A strong default information architecture is:

- identity / introduction
- selected work
- commercial work or capability
- technical / experimental work
- background / credibility
- contact

This is guidance, not a mandatory page order.

## Interaction-budget rule

Interactive/creative elements support identity; they are not the product.

Before rebuilding or extending a hero, particle system, WebGL scene, 3D object, animation, or other expensive visual:
1. check whether the existing implementation can be reused;
2. confirm the change materially improves identity or comprehension;
3. prefer the smallest adaptation;
4. spend implementation effort first on hierarchy, selected work, case-study presentation, trust, and contact.

Do not introduce LiDAR, photogrammetry, Blender/mesh-cleanup pipelines, new rendering frameworks, or heavy 3D asset workflows unless explicitly requested.

For a commercial-facing personal site, prefer:

hero 7/10 + portfolio 10/10

over:

hero 10/10 + incomplete or weak work presentation

## Required outputs

Before implementation, create/update:
- `research/SITE_STRATEGY.md`
- `research/BRAND_BASELINE.md`
- `research/COPY_BASELINE.md` when meaningful
- `research/DESIGN_DIRECTION.md`
- `REFINEMENT_PLAN.md`

`DESIGN_DIRECTION.md` must explicitly state:
- what identity signals remain
- what is removed/reduced
- how expressive/creative sections transition into commercially credible content
- how the site avoids becoming a generic freelancer/agency template

`REFINEMENT_PLAN.md` must explicitly separate:
- reuse
- remove/reduce
- add
- defer

The `defer` section should hold nonessential visual experiments so they do not block shipping.
