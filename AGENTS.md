# Repository purpose

This repository is a control plane for generating production-ready landing-page repositories for high-ticket and luxury industries.

It is NOT where generated landing pages live.

A generated landing must be created as its own repository and be independently deployable.

## Operating modes

The harness has two modes.

### Generate mode

Use when there is no existing demo repository.

Follow `GENERATION_CONTRACT.md`.

### Refine-existing-demo mode

Use when the input includes a Discovery Console `client-brief.json` with:

```json
{
  "refinement": {
    "mode": "refine-existing-demo"
  }
}
```

Read:
1. `DISCOVERY_INPUT_CONTRACT.md`
2. `REFINEMENT_CONTRACT.md`
3. `schemas/client-brief.schema.json`

Then inspect `project.demoRepository` before research or implementation.

In refinement mode, the existing demo is the starting artifact. Do not create a replacement repository and do not regenerate from scratch without a concrete reason.

## Core rule

Never start from generic frontend assumptions.

The agent must first understand:
1. the client
2. the exact industry/subcategory
3. the buyer
4. the category's own visual and commercial language

Human-curated references are optional.

If they are absent, perform research using the deterministic protocol in `RESEARCH_PROTOCOL.md` and the selected industry's `RESEARCH_PLAYBOOK.md`.

## Phase-based context loading

Do not load every skill at once.

Follow `.agents/EFFICIENCY_HARNESS.md`.

### Phase 0 — Input and mode resolution

If a `client-brief.json` is present:

1. validate its schema version
2. identify `project.demoRepository`
3. classify evidence as confirmed / inferred / unknown
4. select refinement mode when `refinement.mode = "refine-existing-demo"`
5. inspect the demo and create `research/DEMO_AUDIT.md`
6. create `research/REFINEMENT_PLAN.md` before editing

For refinement mode, follow `REFINEMENT_CONTRACT.md`.

### Phase 1 — Research

Read:
1. `PRINCIPLES.md`
2. `RESEARCH_PROTOCOL.md`
3. `.agents/EFFICIENCY_HARNESS.md`
4. `industries/<industry>/BRIEF.md`
5. `industries/<industry>/RESEARCH_PLAYBOOK.md` if present
6. `industries/<industry>/REFERENCES.md` only if it contains pinned references
7. client/discovery brief

Then research and create in the target repository.

In generate mode, perform the full research protocol.

In refinement mode, research only unresolved or contradicted gaps after the demo audit and discovery evidence review.


```text
research/
├── MARKET.md
├── COMPETITORS.md
├── REFERENCES.md
└── DESIGN_DIRECTION.md
```

Do not implement before `DESIGN_DIRECTION.md` exists. In refinement mode, `DEMO_AUDIT.md` and `REFINEMENT_PLAN.md` must also exist.

### Phase 2 — Design and implementation

Read:
1. generated `research/DESIGN_DIRECTION.md`
2. `.agents/skills/design-taste-frontend/SKILL.md`
3. `GENERATION_CONTRACT.md`

Implement using the smallest architecture that satisfies the brief.

### Phase 3 — Copy

Read:
1. client/discovery brief
2. generated `research/MARKET.md`
3. industry `BRIEF.md`
4. `.agents/skills/copywriting/SKILL.md`

Write/review final page copy.

### Phase 4 — Release

Read:
1. `GENERATION_CONTRACT.md`
2. `.agents/skills/seo-audit/SKILL.md`
3. implemented site

Run relevant SEO, accessibility, responsive, build, lint, and type checks.

## Research behavior

The agent must navigate research using:
- `RESEARCH_PROTOCOL.md` for the global sequence and stop condition
- `industries/<industry>/RESEARCH_PLAYBOOK.md` for industry-specific queries, entities, terminology, and insider signals

Do not search indefinitely.

Do not treat "looks expensive" as a sufficient reason to select a reference.

Do not turn every high-ticket business into a technology company.

## Content integrity

Do not invent:
- awards
- certifications
- customer logos
- testimonials
- transaction volume
- years in business
- fleet/inventory
- property listings
- medical outcomes
- press coverage
- partnerships
- locations
- statistics

For concept portfolio sites, clearly use fictional brand identities and content that cannot reasonably be mistaken for a real factual claim.

## Forbidden defaults

Avoid:
- generic SaaS layouts
- repeated three-card feature rows
- excessive rounded containers
- excessive gradients
- excessive glassmorphism
- random animations
- black-and-gold luxury clichés
- fake social proof
- generic AI marketing copy
- decorative motion that blocks reading
- placeholder lorem ipsum in a release-ready result
- unnecessary architectural abstraction

## Generated repository default stack

Unless the brief requires otherwise:

- Next.js App Router
- TypeScript, strict
- React Server Components by default
- Tailwind CSS v4
- Bun
- Vercel-compatible build
- no state library
- no UI framework
- no database
- no authentication
- no runtime server dependency
- no animation library unless justified by the design direction

See `GENERATION_CONTRACT.md` and `.agents/EFFICIENCY_HARNESS.md`.

## Definition of done

A landing is not done because it renders.

It must:
- reflect researched category language
- preserve the client's identity instead of imposing a tech aesthetic
- look deliberate rather than templated
- contain credible conversion-oriented copy
- work from small mobile through large desktop
- have complete metadata and crawl/index primitives
- pass the release checklist
- be independently deployable
