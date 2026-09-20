# Post-Discovery Refinement Contract

This contract defines how to turn a discovery brief into a production-ready refinement of an EXISTING demo repository.

The default behavior is refinement, not regeneration.

## 1. Required inputs

Refinement mode requires:

- `client-brief.json`
- an existing demo repository from `project.demoRepository`

Optional:
- current demo URL
- pinned references
- additional client assets
- external documents shared after discovery

If `project.demoRepository` is missing, refinement mode cannot proceed deterministically.

## 2. Evidence precedence

When sources disagree, use this order:

1. confirmed facts from discovery
2. explicit client constraints in discovery
3. current official client website / first-party material
4. existing demo implementation
5. current market/category research
6. inferred discovery notes
7. generic industry defaults

Never let an inference override a confirmed fact.

Never turn an unknown into a factual claim.

## 3. Discovery evidence states

The discovery payload contains:

- `confirmedFacts`
- `inferences`
- `unknowns`

Interpret them as:

### confirmed
Safe to treat as client-provided truth for implementation.

### inferred
Useful working hypothesis. May guide design or research, but must not become a factual claim unless independently confirmed.

### unknown
A known gap. Do not invent it. Research only if it is publicly discoverable and necessary.

## 4. Mandatory first step: inspect the demo

Before researching or editing:

1. inspect the repository tree
2. read the current README
3. identify framework and package manager
4. inspect the main route(s)
5. inspect existing components
6. inspect styling/tokens
7. inspect metadata/SEO
8. inspect current assets
9. identify existing copy assumptions
10. identify existing integrations

Then create:

`research/DEMO_AUDIT.md`

The audit must contain:

- current stack
- current page structure
- current design direction
- reusable strengths
- incorrect assumptions
- confirmed facts already represented correctly
- technical debt relevant to launch
- sections that should remain
- sections that should change
- sections that should be removed

Do not edit before `DEMO_AUDIT.md` exists.

## 5. Preservation rule

Preserve existing work when it is:

- aligned with confirmed discovery
- visually coherent
- technically sound
- useful to the conversion goal
- not contradicted by new research

Do not rewrite code merely for stylistic preference.

Do not replace the framework, router, package manager, styling system, or major dependency structure unless there is a concrete launch-blocking reason.

Do not regenerate the entire site because the agent would personally implement it differently.

## 6. Research in refinement mode

Research is gap-driven.

Start from the normal `RESEARCH_PROTOCOL.md`, but first classify every research topic:

- already confirmed by discovery
- already resolved by good demo work
- unresolved
- contradicted

Only research unresolved or contradicted items.

Typical reasons to research:

- unclear industry terminology
- unclear buyer expectations
- missing trust patterns
- uncertain CTA language
- unresolved visual direction
- missing competitor context
- SEO intent gaps

Do NOT repeat research whose answer is already reliable.

## 7. Refinement research outputs

Refinement mode should create or update:

```text
research/
├── DEMO_AUDIT.md
├── MARKET.md
├── COMPETITORS.md
├── REFERENCES.md
├── DESIGN_DIRECTION.md
└── REFINEMENT_PLAN.md
```

If useful files already exist, update them instead of duplicating them.

## 8. REFINEMENT_PLAN.md

Before changing implementation, produce a concrete change plan.

Required sections:

### Keep
Existing elements that remain substantially unchanged.

### Modify
Existing elements that require focused refinement.

### Remove
Things contradicted by discovery, harmful to credibility, or technically unnecessary.

### Add
Missing sections, assets, metadata, or functionality.

### Research-resolved assumptions
List assumptions from the demo that discovery/research has now confirmed or corrected.

### Unknowns that remain
List remaining gaps that are intentionally not fabricated.

## 9. Change budget

Prefer the smallest coherent set of changes that gets the demo from hypothesis to client-informed production site.

Do not optimize for diff size alone, but avoid full rewrites without cause.

A refinement should normally preserve:
- repository identity/history
- working deployment setup
- useful components
- correct content structure
- valid design decisions

## 10. Copy behavior

Replace speculative demo copy with:

- confirmed client facts
- validated industry terminology
- approved proof
- accurate CTA language

Never retain demo claims that discovery contradicts.

Never invent proof to make the final page feel more complete.

## 11. Design behavior

The refined design must trace to:

- confirmed client identity
- discovery preferences
- industry brief
- gap research
- existing demo strengths

The final site should feel like a better-informed version of the demo, not an unrelated second pitch.

## 12. Technical behavior

Follow `.agents/EFFICIENCY_HARNESS.md`.

In refinement mode:
- do not migrate frameworks for taste
- do not introduce libraries without need
- do not refactor stable code outside the refinement scope
- keep client JS minimal
- preserve working deployment configuration unless incorrect

## 13. Completion gate

Refinement is complete only when:

- demo assumptions have been audited
- confirmed discovery facts are reflected correctly
- contradicted assumptions are removed
- research gaps are resolved or explicitly left unknown
- `REFINEMENT_PLAN.md` is implemented
- design direction reflects the client rather than the initial guess
- copy contains no unsupported factual claims
- release checks pass
- the site remains deployable
