# Agent Efficiency Harness

The objective is a deploy-ready marketing landing, not a general-purpose frontend platform.

Optimize for:
1. correct visual direction
2. credible copy
3. fast page delivery
4. minimal implementation complexity
5. minimal context and token waste

Complexity must earn its place.

## 1. Progressive context loading

Do NOT load every skill at the start.

Use this sequence:

### Research phase
Read only:
- `PRINCIPLES.md`
- `RESEARCH_PROTOCOL.md`
- industry `BRIEF.md`
- industry `RESEARCH_PLAYBOOK.md` if present
- client/discovery brief

Do not load SEO or copywriting skill yet.

### Design phase
Additionally read:
- `.agents/skills/design-taste-frontend/SKILL.md`
- generated `research/DESIGN_DIRECTION.md`

Use the skill to make concrete decisions, then stop rereading it.

### Copy phase
Read:
- client brief
- `research/MARKET.md`
- industry brief
- `.agents/skills/copywriting/SKILL.md`

Do not reread the full design skill unless a design/copy conflict appears.

### Release phase
Read:
- `GENERATION_CONTRACT.md`
- `.agents/skills/seo-audit/SKILL.md`
- implemented site

Run only the relevant SEO checks for the generated site.

## 2. Default architecture budget

For a normal single-page landing, default to:

- 1 route
- 1 layout
- 1 page
- 5-10 semantic page sections
- 0 state-management libraries
- 0 UI component frameworks
- 0 data-fetching libraries
- 0 form libraries unless validation complexity requires one
- 0 animation libraries unless the design direction explicitly benefits from motion
- 0 custom hooks unless behavior is genuinely reused
- 0 context providers unless required
- 0 backend/database/authentication unless requested

These are defaults, not hard technical limits. Exceed them only with a concrete reason.

## 3. Component extraction rule

Do not componentize for ceremony.

Create a component only when at least one is true:

1. it is reused
2. it owns a substantial semantic section
3. it isolates client-side behavior
4. it materially improves readability of `page.tsx`

Do not create:
- one-line wrapper components
- components used once solely to make the file tree look architectural
- generic primitives that Tailwind/native HTML already express clearly
- a design-system package for one landing page

A typical single-page landing should usually need roughly 5-12 project-specific components, not dozens.

## 4. Client JavaScript budget

Default: server-rendered/static.

Client Components are allowed only for:
- navigation behavior that needs state
- form interaction
- gallery/carousel behavior
- purposeful motion
- other actual browser interaction

Do not mark an entire page `"use client"` to make one element interactive.

Prefer CSS for:
- hover
- focus
- simple transitions
- responsive layout
- simple reveal effects when they can be implemented accessibly without JS

## 5. Styling budget

Prefer:
- Tailwind utilities
- a small set of CSS custom properties in `globals.css`
- semantic section-level components

Avoid:
- creating a token generation pipeline
- CSS-in-JS
- theme providers for a one-theme site
- utility wrappers around Tailwind
- dozens of bespoke spacing variables

Define only tokens actually used by the site.

## 6. Dependency rule

Every dependency must answer:

"What does this provide that the platform, Next.js, React, or CSS cannot provide simply enough?"

If the answer is weak, do not install it.

Default dependencies should be close to:
- next
- react
- react-dom
- Tailwind/PostCSS tooling

Add Motion only when justified by `DESIGN_DIRECTION.md`.

Add an icon library only if the design actually uses multiple icons.

## 7. Content/data rule

For concept/portfolio landings:
- keep small static content close to the component that owns it
- use a simple typed data file only when repeated data benefits from it
- do not add CMS abstractions
- do not create repositories/services/hooks for static content
- do not add JSON schemas unless another system actually consumes them

## 8. Test budget

For a mostly static marketing landing, mandatory quality gates are:

- lint
- TypeScript
- production build
- responsive visual check
- keyboard/accessibility check
- broken-link/form behavior check

Do not build a large unit-test suite for static markup.

Add automated behavior tests only when meaningful behavior exists.

## 9. Research token discipline

Never paste full competitor pages into research files.

Store concise findings.

Per competitor/reference, target roughly:
- one positioning sentence
- 5-8 observations maximum

Stop searching once the stop condition in `RESEARCH_PROTOCOL.md` is satisfied.

## 10. Implementation discipline

Prefer one coherent implementation pass over speculative abstractions.

Before adding a new file, dependency, abstraction, or architectural layer, ask:

- Is it required by the brief?
- Is it required by the generation contract?
- Is it reused?
- Does it reduce complexity rather than merely move it?

If all answers are no, do not add it.

## 11. No premature generalization

Generated landing repositories are disposable, independent deliverables.

Do not make them extensible for hypothetical future products, dashboards, CMSs, locales, themes, or apps unless requested.

The control plane repository is where reusable knowledge lives.

The generated repo should remain boring technically and distinctive visually.
