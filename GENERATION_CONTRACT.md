# Landing Repository Generation Contract

This document defines **generate mode**: creating a landing when no existing demo repository is supplied.

The output is a NEW repository, not a subfolder of this repository.

If a Discovery Console payload specifies `refinement.mode = "refine-existing-demo"`, this contract is not the orchestration entrypoint. Use `REFINEMENT_CONTRACT.md` and refine the existing repository instead.

## 1. Required inputs

At minimum:
- industry
- brand name
- whether the brand is real or fictional
- target audience
- primary offer
- primary conversion action
- target geography if locally relevant

Preferred input is a completed discovery/client brief.

If information is missing, infer only low-risk creative details. Never invent claims presented as factual proof.

## 2. Mandatory research gate

Before implementation, follow:
- `RESEARCH_PROTOCOL.md`
- the selected industry's `RESEARCH_PLAYBOOK.md`

Human-pinned references are optional.

Use the `generate-landing` skill as the orchestration entrypoint. Do not preload all supporting skills.

Asset generation is not a research or implementation requirement. Default generated-asset budget is zero; follow the `landing-assets` skill.

The generated repository must contain:

```text
research/
├── MARKET.md
├── COMPETITORS.md
├── REFERENCES.md
└── DESIGN_DIRECTION.md
```

Implementation may begin only after `DESIGN_DIRECTION.md` exists.

## 3. Output repository

Default repository naming:

`landing-<brand-slug>`

The generated repository should remain technically small.

Minimum structure:

```text
.
├── app/
│   ├── layout.tsx
│   ├── page.tsx
│   ├── globals.css
│   ├── robots.ts
│   └── sitemap.ts
├── components/
├── public/
├── research/
│   └── ASSET_MANIFEST.md   # only when temporary/external assets are used
├── .github/workflows/ci.yml
├── .gitignore
├── README.md
├── bun.lock
├── eslint.config.*
├── next.config.*
├── package.json
├── tsconfig.json
└── AGENTS.md
```

Add routes and files only when they serve the brief.

## 4. Technical baseline

Default:
- current stable Next.js App Router
- current stable React supported by Next.js
- TypeScript strict mode
- Tailwind CSS v4
- Bun
- Server Components unless interactivity requires a Client Component
- `next/font` or legally self-hosted font files
- optimized `next/image` usage where appropriate

Follow `.agents/EFFICIENCY_HARNESS.md`.

Avoid introducing dependencies when platform primitives are sufficient.

## 5. Visual system

Before building sections, define in `research/DESIGN_DIRECTION.md`:

- page background
- primary and muted text
- accent
- border treatment
- typography direction
- type scale
- spacing rhythm
- content width
- shape/radius rule
- image treatment
- composition rules
- motion rule
- density rule

These decisions must trace back to:
- client identity
- industry brief
- current research
- selected references

Do not create a universal "luxury" style.

## 6. Copy requirements

Run the copywriting skill in the copy phase.

The page must have:
- a specific H1
- a supporting value proposition
- one primary conversion action
- industry-appropriate CTA language
- objection handling where useful
- no unsupported superlatives
- no filler copy
- no fake proof

For portfolio concepts, fictional copy should sound plausible without fabricating external validation.

## 7. SEO baseline

Run the SEO audit skill as a release gate, not during initial implementation.

Every release-ready site must include:
- unique title
- useful meta description
- canonical strategy
- one clear H1
- semantic heading hierarchy
- descriptive image alt text
- crawlable internal links
- `robots.ts`
- `sitemap.ts`
- Open Graph metadata
- Twitter/X metadata where applicable
- favicon/app icons if assets exist
- structured data only when the underlying facts actually exist

Local-business concepts should be structured so appropriate local schema can be added when real NAP data exists, but must not fabricate NAP values.

## 8. Accessibility baseline

Required:
- keyboard-usable navigation and controls
- visible focus states
- semantic interactive elements
- sufficient contrast
- reduced-motion handling for non-essential motion
- accessible labels for forms and controls
- no information conveyed only by color
- no hover-only essential interaction

## 9. Performance baseline

Design for:
- minimal client JavaScript
- responsive image sizes
- lazy loading below the fold
- no autoplay heavyweight video on constrained mobile unless justified
- stable layout with explicit media dimensions
- no unnecessary third-party scripts

Prefer visual restraint over effect-heavy performance debt.

## 10. Forms

Concept repos should default to a UI-complete contact/inquiry form without pretending submissions are persisted.

If a real backend is requested:
- isolate provider integration
- document required environment variables
- provide `.env.example`
- never commit credentials

## 11. Analytics

Do not add trackers by default.

If analytics is requested, prefer a documented provider integration and keep it removable.

## 12. CI

Generated repositories must contain a GitHub Actions workflow using Bun that runs at least:

```bash
bun install --frozen-lockfile
bun run lint
bun run typecheck
bun run build
```

Add tests only when there is meaningful behavior worth testing.

## 13. Deployment

Default deployment target: Vercel.

README must contain:
- local development command
- production build command
- required environment variables
- deployment notes
- asset/license notes if relevant

A project requiring no environment variables should say so explicitly.

## 14. Release checklist

Before declaring the generated repository ready:

### Research
- [ ] MARKET.md exists
- [ ] COMPETITORS.md exists
- [ ] REFERENCES.md exists
- [ ] DESIGN_DIRECTION.md exists
- [ ] research stop condition was reached
- [ ] references have distinct jobs

### Assets
- [ ] no unnecessary generated assets
- [ ] any temporary/external demo assets are documented
- [ ] production licensing/replacement needs are explicit

### Design
- [ ] industry brief is visibly reflected
- [ ] client's identity is preserved
- [ ] no generic AI/SaaS composition
- [ ] no unjustified luxury cliché
- [ ] typography hierarchy is consistent
- [ ] shape system is consistent
- [ ] image crop/art direction works at all breakpoints
- [ ] motion has a purpose
- [ ] reduced-motion behavior exists where needed

### Content
- [ ] H1 is specific
- [ ] primary CTA is explicit
- [ ] no lorem ipsum
- [ ] no invented proof
- [ ] no empty placeholder sections
- [ ] tone matches the industry

### Responsive
- [ ] 320px
- [ ] 375/390px
- [ ] 768px
- [ ] 1024px
- [ ] 1440px+
- [ ] navigation works without overflow
- [ ] display type does not clip or wrap badly

### Accessibility
- [ ] keyboard navigation checked
- [ ] focus states visible
- [ ] contrast checked
- [ ] form labels checked
- [ ] alt text checked

### SEO
- [ ] title
- [ ] description
- [ ] canonical strategy
- [ ] H1/heading hierarchy
- [ ] robots
- [ ] sitemap
- [ ] social metadata
- [ ] no fake schema data

### Engineering
- [ ] architecture stays within the efficiency harness unless justified
- [ ] `bun install --frozen-lockfile`
- [ ] lint passes
- [ ] typecheck passes
- [ ] build passes
- [ ] no secrets committed
- [ ] README is complete

## 15. Handoff

When generation is complete, report:
- repository URL
- branch/commit
- research summary
- what is fictional vs. factual
- deployment requirements
- remaining manual asset/licensing work
- any intentionally omitted integrations
- any efficiency-budget exception and why it was necessary
