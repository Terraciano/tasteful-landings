# Tasteful Sites (repo: tasteful-landings)

A control repository for generating deploy-ready institutional/business websites for high-ticket, specialist and luxury industries.

This repo stores:
- global design principles
- deterministic research rules
- industry-specific briefs and research playbooks
- vendored agent skills for design, copywriting, and SEO
- an efficiency harness
- project-local Codex multi-agent configuration
- lazy-loaded workflow skills
- explicit zero-by-default generated-asset policy
- site strategy that distinguishes institutional sites from campaign landings
- the production contract every generated site must satisfy

It does **not** store generated sites themselves.

## Current industry packs

- Private aviation
- Wineries / wine estates
- Olive estates / premium olive oil
- Luxury real estate
- Yachting / yacht brokerage
- Luxury construction / architecture
- Collector / exotic automotive
- Private medical / cosmetic / longevity
- Boutique hospitality / villas / resorts
- Wealth management / family office
- High-end interiors
- High-end legal / advisory
- Fine jewelry / watches
- Luxury home services

## Agent entrypoint

Read `AGENTS.md`.

There are two lifecycle flows. Site type is resolved separately.

### First-contact / demo generation


```text
PUBLIC INFORMATION
    ↓
SITE STRATEGY
institutional (default) | campaign
single-page | multi-page
    ↓
FIRST-PARTY BRAND + COPY EXTRACTION
    ↓
BRAND_BASELINE.md + COPY_BASELINE.md
    +
PRINCIPLES
    +
INDUSTRY BRIEF
    ↓
DETERMINISTIC MARKET / COMPETITOR / VISUAL RESEARCH
    ↓
MARKET.md
COMPETITORS.md
REFERENCES.md
DESIGN_DIRECTION.md
    ↓
DESIGN SKILL
    ↓
VITE + VANILLA TS/CSS BY DEFAULT
    ↓
LEAN STATIC IMPLEMENTATION
    ↓
COPY SKILL
    ↓
SEO + RELEASE QA
    ↓
NEW DEMO REPOSITORY
```

### Post-discovery refinement

```text
DISCOVERY CALL
    ↓
Discovery Console
    ↓
client-brief.json
    +
EXISTING DEMO REPO
    ↓
DEMO_AUDIT.md
    ↓
GAP-ONLY RESEARCH
    ↓
DESIGN_DIRECTION.md
REFINEMENT_PLAN.md
    ↓
FOCUSED REFINEMENT
    ↓
COPY + SEO + RELEASE QA
    ↓
PRODUCTION-READY EXISTING REPO
```

The final workflow does not regenerate a second site by default. It turns the original demo from a public-information hypothesis into a client-informed production artifact.

Human-curated references are optional.

If the user pins a reference in `industries/<industry>/REFERENCES.md`, the agent must inspect it. Otherwise the agent discovers project-specific references itself.

## Efficiency model

The harness is optimized around current Codex behavior:

- root `AGENTS.md` is intentionally short because project instructions are injected persistently
- workflow details live in Skills and load progressively
- one main agent owns synthesis + implementation
- Luna read-only subagents handle cheap exploration/extraction
- Terra is reserved for visual analysis and final review
- concurrency is capped at 3
- generated assets default to zero
- first-party brand CSS/tokens are inspected before inventing visual direction
- Vite + vanilla TypeScript/CSS is the default frontend stack
- Astro is the static-complexity escape hatch
- Next.js is an exception, not the baseline
- Cloudflare Pages is the default deployment target
- GitHub remote creation/push and deployment are manual/human-owned; Codex stops at a build-ready local repository

Skills are loaded by phase instead of all at once.

Generated repos should be technically boring and visually distinctive.

The default institutional site should usually be static Vite output and should not need:
- React or another UI framework
- a state library
- a CMS
- a database
- dozens of components
- speculative abstractions
- a large unit-test suite

See `.agents/EFFICIENCY_HARNESS.md`.

## Expected request style

Example:

> Generate a first-contact institutional site for a private-aircraft brokerage named Northstar Aviation. Preserve specialist credibility and company narrative; choose single vs multi-page from the content. Create a build-ready local repository.

The agent should resolve institutional vs campaign and single vs multi-page before choosing information architecture or copy.

## Repository map

```text
.
├── .codex/
│   ├── config.toml
│   └── agents/
├── .agents/
│   ├── EFFICIENCY_HARNESS.md
│   ├── product-marketing.template.md
│   └── skills/
├── industries/
│   ├── _template/
│   └── aviation/
│       ├── BRIEF.md
│       ├── REFERENCES.md
│       └── RESEARCH_PLAYBOOK.md
├── schemas/
│   └── client-brief.schema.json
├── AGENTS.md
├── DISCOVERY_INPUT_CONTRACT.md
├── GENERATION_CONTRACT.md
├── REFINEMENT_CONTRACT.md
├── PRINCIPLES.md
├── RESEARCH_PROTOCOL.md
├── THIRD_PARTY_SKILLS.md
└── README.md
```

## Human work still required

Remote publication and deployment are deliberately manual.

The harness output is a **local repository**.

Codex must not:
- create the GitHub repository
- configure `origin`
- push
- open Cloudflare
- run Wrangler
- deploy
- configure DNS
- verify production

The human operator handles all of that after handoff.

Codex should prepare the repository and document:
- `bun run build`
- output directory (`dist` for default Vite)
- required environment variables
- domain/DNS notes

It must not open Cloudflare, run Wrangler, deploy, configure DNS, or verify production unless explicitly asked.

The primary human input should be:
- good discovery with the client
- any non-negotiable brand/reference direction
- access to real brand assets and factual proof
- approval/licensing of final production imagery and fonts

Manual moodboard curation is not required for every project.
