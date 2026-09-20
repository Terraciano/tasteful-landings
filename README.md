# Tasteful Landings

A control repository for generating deploy-ready landing-page repositories for high-ticket and luxury industries.

This repo stores:
- design principles
- industry-specific design briefs
- curated reference frameworks
- vendored agent skills for design, copywriting, and SEO
- the production contract every generated landing must satisfy

It does **not** store the generated sites themselves.

## Current industry pack

- Private aviation

More industry packs should be added only when their visual language, commercial behavior, trust signals, and conversion patterns have been researched.

## Agent entrypoint

Read `AGENTS.md`.

The core flow is:

```text
PRINCIPLES
    +
GENERATION CONTRACT
    +
INDUSTRY BRIEF
    +
CURATED REFERENCES
    +
DESIGN / COPY / SEO SKILLS
    ↓
AGENT
    ↓
NEW LANDING REPOSITORY
    ↓
CI + VERCEL-READY BUILD
```

## Expected command/request style

Example:

> Generate a fictional private-aircraft brokerage landing named Northstar Aviation. Target aircraft owners and buyers in South Florida. Primary CTA: Request aircraft details. Create it as a separate deploy-ready repository.

The agent should use the repository contract rather than inventing a design system from scratch.

## Repository map

```text
.
├── .agents/
│   ├── product-marketing.template.md
│   └── skills/
├── industries/
│   └── aviation/
│       ├── BRIEF.md
│       └── REFERENCES.md
├── AGENTS.md
├── GENERATION_CONTRACT.md
├── PRINCIPLES.md
├── THIRD_PARTY_SKILLS.md
└── README.md
```

## Human work still required

The highest-value human input is reference curation and asset licensing.

Do not automate taste by blindly scraping inspiration sites. Approve the references that actually fit each vertical, then let the agent execute within those constraints.
