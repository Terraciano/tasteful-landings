# Tasteful Landings

A control repository for generating deploy-ready landing-page repositories for high-ticket, specialist and luxury industries.

This repo stores:
- global design principles
- deterministic research rules
- industry-specific briefs and research playbooks
- vendored agent skills for design, copywriting, and SEO
- an efficiency harness
- the production contract every generated landing must satisfy

It does **not** store generated sites themselves.

## Current industry pack

- Private aviation

## Agent entrypoint

Read `AGENTS.md`.

The flow is:

```text
CLIENT DISCOVERY
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
LEAN IMPLEMENTATION
    ↓
COPY SKILL
    ↓
SEO + RELEASE QA
    ↓
NEW DEPLOY-READY REPOSITORY
```

Human-curated references are optional.

If the user pins a reference in `industries/<industry>/REFERENCES.md`, the agent must inspect it. Otherwise the agent discovers project-specific references itself.

## Efficiency model

Skills are loaded by phase instead of all at once.

Generated repos should be technically boring and visually distinctive.

The default single-page landing should not need:
- a UI framework
- a state library
- a CMS
- a database
- dozens of components
- speculative abstractions
- a large unit-test suite

See `.agents/EFFICIENCY_HARNESS.md`.

## Expected request style

Example:

> Generate a fictional private-aircraft brokerage landing named Northstar Aviation. Target aircraft owners and buyers in South Florida. Primary CTA: Request aircraft details. Create it as a separate deploy-ready repository.

The agent should research the current category before choosing a design direction.

## Repository map

```text
.
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
├── AGENTS.md
├── GENERATION_CONTRACT.md
├── PRINCIPLES.md
├── RESEARCH_PROTOCOL.md
├── THIRD_PARTY_SKILLS.md
└── README.md
```

## Human work still required

The primary human input should be:
- good discovery with the client
- any non-negotiable brand/reference direction
- access to real brand assets and factual proof
- approval/licensing of final production imagery and fonts

Manual moodboard curation is not required for every project.
