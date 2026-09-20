# Tasteful Sites — Codex routing

This repository is the control plane. Client sites live in separate target repositories.

## Resolve the mode first

- No existing demo repo → use the `generate-landing` skill in site-generation mode.
- Discovery JSON with `refinement.mode = "refine-existing-demo"` → use the `refine-landing` skill.

Do not execute both workflows.

## Persistent rules

- Default project type is an institutional brand/business site, not a campaign landing.
- Campaign landing behavior is opt-in: use only when explicitly requested or clearly required by the brief.
- Preserve niche/category identity; do not default to SaaS/startup aesthetics.
- Never invent awards, clients, testimonials, statistics, credentials, locations, inventory, transaction history, or other proof.
- Human references are optional.
- Keep generated repos technically boring and visually distinctive.
- Default generated-asset budget is zero. Use the `landing-assets` skill for asset decisions.
- Keep one implementation writer. Subagents are for focused read-heavy work and review, not parallel code writing.
- Stop research when uncertainty is resolved.
- Load design, copy, and SEO skills only in the phase where they are needed.
- Prefer the smallest architecture/change set that satisfies the active contract.
- Output is a local repository only. Never create a GitHub repository, add/configure a remote, push commits, deploy, open Cloudflare, run Wrangler, authenticate, configure DNS, or inspect production unless the user explicitly asks for that action in the current task.

## Source locations

- Global principles: `PRINCIPLES.md`
- Industry guidance: `industries/<industry>/`
- Generate contract: `GENERATION_CONTRACT.md`
- Refinement contract: `REFINEMENT_CONTRACT.md`
- Research protocol: `RESEARCH_PROTOCOL.md`
- Efficiency: `.agents/EFFICIENCY_HARNESS.md`
- Discovery schema: `schemas/client-brief.schema.json`

Do not preload all of these. The selected workflow skill decides what to read.
