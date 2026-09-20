# Codex Architecture

This repository is optimized for current Codex project configuration, Skills, and subagents.

## Design goals

1. Keep persistent prompt/context small.
2. Use progressive disclosure for workflow instructions.
3. Use cheap read-only agents for noisy exploration.
4. Keep synthesis and code writing in one strong main agent.
5. Avoid asset-generation work unless explicitly valuable.
6. Stop research and delegation as soon as uncertainty is resolved.

## Main session

Configured in `.codex/config.toml`:

- model: `gpt-5.6`
- reasoning: `medium`

The main session owns:
- mode selection
- research synthesis
- design direction
- implementation
- copy decisions
- final fixes

This is intentionally not delegated because these decisions share context and benefit from one coherent writer.

## Subagents

### market_researcher
`gpt-5.6-luna`, medium, read-only.

Use for:
- category terminology
- competitor scans
- trust signals
- buyer/search intent

### repo_explorer
`gpt-5.6-luna`, medium, read-only.

Use only in refinement mode to map the existing demo.

### visual_researcher
`gpt-5.6-terra`, medium, read-only.

Conditional. Spawn only when visual direction remains unresolved after market/category research.

### reviewer
`gpt-5.6-terra`, high, read-only.

Use at the end for concrete release risks.

## Why no writer subagent

Parallel read-heavy work can reduce main-thread context pollution.

Parallel writing creates coordination overhead, inconsistent direction, and merge conflicts for a small landing-page task.

The main agent therefore remains the only implementation writer by default.

## Skills

Root `AGENTS.md` only routes work.

Long workflows are lazy-loaded through:
- `generate-landing`
- `refine-landing`
- `landing-assets`
- vendored design/copy/SEO skills

This avoids permanently injecting the entire process into every task.

## Asset strategy

Generated assets are opt-in.

For demos:
- prefer prospect/client assets
- use a very small number of temporary first-party public images when appropriate
- document them in `ASSET_MANIFEST.md`
- otherwise use typography, CSS, whitespace, or intentional asset slots

Do not spend agent runs synthesizing decorative images, SVG art, icons, logos, or video.

## Concurrency

Maximum subagent concurrency: 3.

This is a ceiling, not a target.

Typical generate run:
- main agent
- market researcher
- visual researcher only if needed

Typical refinement run:
- main agent
- repo explorer
- one gap researcher if needed
- reviewer after implementation

## Official Codex references

Architecture decisions track the current OpenAI documentation for:
- project config: https://developers.openai.com/docs/config-file/config-basic
- config reference: https://developers.openai.com/docs/config-file/config-reference
- subagents: https://developers.openai.com/docs/agent-configuration/subagents
- AGENTS.md: https://developers.openai.com/docs/agent-configuration/agents-md
- Skills: https://developers.openai.com/docs/build-skills

Re-check these docs when upgrading the harness because agent configuration can evolve.
