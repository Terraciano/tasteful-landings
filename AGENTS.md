# Repository purpose

This repository is a control plane for generating production-ready landing-page repositories for high-ticket and luxury industries.

It is NOT the repository where generated landing pages live.

A generated landing must be created as its own repository and be deployable independently.

## Mandatory sources of truth

Before generating or modifying a landing repository, read in this order:

1. `PRINCIPLES.md`
2. `GENERATION_CONTRACT.md`
3. the selected industry's `industries/<industry>/BRIEF.md`
4. the selected industry's `industries/<industry>/REFERENCES.md`
5. `.agents/skills/design-taste-frontend/SKILL.md`
6. `.agents/skills/copywriting/SKILL.md`
7. `.agents/skills/seo-audit/SKILL.md`

If the target repository already exists, inspect it before making changes.

## Core rule

Never start from generic frontend assumptions.

The industry brief controls visual language, audience, trust signals, information hierarchy, photography direction, and conversion behavior.

The design skill controls execution quality and anti-slop checks.

The copywriting skill controls persuasive structure and wording.

The SEO skill is a release gate, not an afterthought.

## Generation workflow

1. Read the required sources of truth.
2. Produce a short internal design read.
3. Define the page's primary conversion action.
4. Establish the information architecture and section order.
5. Establish design tokens and typography before component implementation.
6. Implement the landing repository.
7. Run copy review.
8. Run technical SEO review.
9. Run responsive, accessibility, and visual QA.
10. Run build, lint, and type checks.
11. Only then consider the repository release-ready.

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

## Generated repository default stack

Unless the brief requires otherwise:

- Next.js App Router
- TypeScript, strict
- React Server Components by default
- Tailwind CSS v4
- Motion only when motion has a defined purpose
- Bun as package manager
- Vercel-compatible build
- no database
- no authentication
- no runtime server dependency unless required by the brief

See `GENERATION_CONTRACT.md` for the full output contract.

## Definition of done

A landing is not done because it renders.

It must:
- look deliberate rather than templated
- fit the target industry's visual language
- contain credible conversion-oriented copy
- work from small mobile through large desktop
- have complete metadata and crawl/index primitives
- pass the release checklist in `GENERATION_CONTRACT.md`
- be independently deployable
