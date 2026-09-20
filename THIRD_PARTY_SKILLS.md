# Vendored Agent Skills

The repository vendors third-party skills so generated work does not depend on machine-global skill installation.

## design-taste-frontend

Source:
https://github.com/Leonxlnx/taste-skill

Install name:
`design-taste-frontend`

Vendored from:
`skills/taste-skill/SKILL.md`

Upstream status at time of vendoring:
v2 / experimental.

## seo-audit

Source:
https://github.com/coreyhaines31/marketingskills

Install name:
`seo-audit`

Vendored with its referenced Markdown files.

## copywriting

Source:
https://github.com/coreyhaines31/marketingskills

Install name:
`copywriting`

Vendored with its referenced Markdown files.

## Updating

Do not silently overwrite these files.

When updating a vendored skill:
1. review the upstream diff
2. verify it does not conflict with this repository's `PRINCIPLES.md` or `GENERATION_CONTRACT.md`
3. replace the vendored files
4. record the update in git history

Repository-local instructions take precedence when an upstream skill conflicts with the purpose of this project.
