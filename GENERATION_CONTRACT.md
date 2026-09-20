# Landing Repository Generation Contract

This document defines **generate mode**: creating a landing when no existing demo repository is supplied.

The output is a NEW repository, not a subfolder of this repository.

If a Discovery Console payload specifies `refinement.mode = "refine-existing-demo"`, use `REFINEMENT_CONTRACT.md` instead.

## 1. Required inputs

At minimum:
- industry
- brand name
- whether the brand is real or fictional
- target audience
- primary offer
- primary conversion action
- target geography if locally relevant

If information is missing, infer only low-risk creative details. Never invent factual proof.

## 2. Mandatory research gate

Use `generate-landing` as the orchestration entrypoint.

Before implementation:
- inspect first-party identity with `extract-brand-baseline` when an existing site is available
- follow `RESEARCH_PROTOCOL.md`
- follow the selected industry `RESEARCH_PLAYBOOK.md`
- follow `landing-assets`

Default generated-asset budget is zero.

Required research files:

```text
research/
├── BRAND_BASELINE.md   # when a first-party site exists
├── MARKET.md
├── COMPETITORS.md
├── REFERENCES.md
└── DESIGN_DIRECTION.md
```

Implementation may begin only after `DESIGN_DIRECTION.md` exists.

## 3. Framework selection

Choose the smallest stack that satisfies the brief.

### Default: Vite + vanilla TypeScript

Use for normal marketing sites and landing pages.

Baseline:
- Vite
- vanilla TypeScript
- semantic HTML
- CSS
- Bun
- static `dist/`
- Cloudflare Pages

React is not part of the default stack.

### Astro

Use only when the site materially benefits from:
- multiple static routes
- reusable layouts
- content collections
- repeated structured content
- static-site composition that would otherwise become awkward in plain HTML

Astro must still deploy as static output unless runtime behavior is explicitly required.

### Next.js / full app framework

Use only when there is a concrete application/runtime requirement such as:
- authenticated application behavior
- server-side runtime logic
- complex dynamic routing/data requirements
- server actions/API behavior that genuinely belongs in this project

SEO alone is not justification for Next.js.

Framework familiarity is not justification.

Document any escalation beyond vanilla Vite in the README.

## 4. Default Vite repository

Typical single-page structure:

```text
.
├── index.html
├── src/
│   ├── main.ts
│   └── styles.css
├── public/
│   ├── robots.txt
│   └── sitemap.xml
├── research/
├── .github/workflows/ci.yml
├── .gitignore
├── README.md
├── bun.lock
├── package.json
└── tsconfig.json
```

Add files only when the brief requires them.

For multiple pages, use additional static HTML entries or escalate to Astro when that becomes materially clearer.

## 5. Brand fidelity gate

If a first-party site exists, `BRAND_BASELINE.md` is required.

Before selecting palette/typography/UI accents, verify:
- recurring CSS color values/tokens
- font families and weights
- logo treatment
- navigation/button treatment
- recurring shape/border/radius cues
- photography/media language

`DESIGN_DIRECTION.md` must state:
- what existing identity is preserved
- what is intentionally reinterpreted
- justification for any newly introduced accent/font/system

Never invent a new brand color merely for visual novelty.

## 6. Visual system

Before implementation, define in `DESIGN_DIRECTION.md`:
- background/surfaces
- primary and muted text
- accent(s)
- border treatment
- typography direction
- type scale
- spacing rhythm
- content width
- shape/radius rule
- media treatment
- composition rules
- motion rule
- density rule

Decisions must trace to brand baseline, client identity, industry brief, and current research.

## 7. SEO baseline

Static HTML is the preferred SEO delivery model for these sites.

Every release-ready site must include:
- unique `<title>`
- useful meta description
- canonical URL strategy
- one clear H1
- semantic heading hierarchy
- descriptive alt text
- crawlable links
- `robots.txt`
- `sitemap.xml`
- Open Graph metadata
- social metadata where applicable
- structured data only when facts are real

Do not add a framework merely for metadata generation.

## 8. Copy

Run the copywriting skill only in the copy phase.

Require:
- specific H1
- supporting value proposition
- explicit primary CTA
- industry-appropriate wording
- no unsupported superlatives
- no filler
- no fake proof

## 9. Assets

Default generated-asset budget: zero.

- prefer client/first-party/existing assets
- document temporary assets in `research/ASSET_MANIFEST.md`
- use intentional image-light composition or asset slots rather than generating decorative filler
- never invent a synthetic logo for a real prospect

## 10. Accessibility

Required:
- keyboard-usable controls
- visible focus states
- semantic elements
- sufficient contrast
- reduced-motion handling where relevant
- labels for forms
- no hover-only essential behavior

## 11. Performance

Prefer:
- no framework runtime
- minimal JS
- responsive optimized images
- lazy loading below fold
- explicit media dimensions
- no unnecessary third-party scripts

## 12. Forms

Demo forms may be UI-complete without pretending submissions persist.

For production, add a Cloudflare-compatible provider or endpoint only when requested.

Document environment variables and never commit credentials.

## 13. Deployment

Default deployment target: **Cloudflare Pages**.

For Vite:
- build command: `bun run build`
- output directory: `dist`

The generated README must document:
- local dev command
- production build command
- Cloudflare Pages build settings
- required environment variables
- domain/DNS notes
- asset/license notes

If runtime/server behavior becomes necessary, evaluate Cloudflare Workers instead of introducing a non-Cloudflare hosting assumption.

Do not target Vercel by default.

## 14. CI

Default CI:

```bash
bun install --frozen-lockfile
bun run typecheck
bun run build
```

Add lint only when a configured linter exists.

Add tests only for meaningful behavior.

## 15. Release checklist

### Research
- [ ] BRAND_BASELINE.md exists when a first-party site exists
- [ ] MARKET.md exists
- [ ] COMPETITORS.md exists
- [ ] REFERENCES.md exists
- [ ] DESIGN_DIRECTION.md exists
- [ ] research stop condition reached

### Brand
- [ ] first-party colors checked directly
- [ ] first-party typography checked where discoverable
- [ ] no invented conflicting accent colors
- [ ] design direction documents preserve/reinterpret decisions

### Assets
- [ ] no unnecessary generated assets
- [ ] temporary assets documented
- [ ] production replacement/licensing needs explicit

### Design/content
- [ ] niche/industry identity visible
- [ ] H1 and CTA specific
- [ ] no fake proof
- [ ] no generic SaaS composition
- [ ] no unjustified luxury cliché

### Responsive/accessibility
- [ ] 320px
- [ ] 375/390px
- [ ] 768px
- [ ] 1024px
- [ ] 1440px+
- [ ] keyboard/focus checked
- [ ] contrast checked
- [ ] alt text checked

### SEO
- [ ] title
- [ ] description
- [ ] canonical
- [ ] heading hierarchy
- [ ] robots.txt
- [ ] sitemap.xml
- [ ] social metadata
- [ ] no fake schema

### Engineering
- [ ] framework choice is minimal and justified
- [ ] Cloudflare deployment documented
- [ ] `bun install --frozen-lockfile`
- [ ] typecheck passes
- [ ] build passes
- [ ] no secrets
- [ ] README complete

## 16. Handoff

Report:
- repository URL
- branch/commit
- framework choice and why
- research summary
- what is factual vs inferred
- temporary assets
- Cloudflare deployment requirements
- any remaining manual work
