---
name: landing-assets
description: Decide how a landing should handle images, icons, logos, video, and other visual assets while minimizing generation time and token use. Use during demo generation or refinement whenever assets are needed.
---

# Asset policy

Default generated-asset budget: **zero**.

Do not generate:
- AI hero images
- decorative illustrations
- custom SVG scenes
- synthetic logos
- icon sets
- textures
- background art
- videos

unless the user explicitly requests generated assets or the design cannot function without one and no cheaper substitute exists.

## Priority order

Use assets in this order:

1. client-provided assets
2. existing assets already in the demo repository
3. clearly relevant first-party public assets from the prospect for a private demo, documented as temporary/reference-only
4. lightweight licensed/stock assets when available and appropriate
5. CSS / typography / whitespace / simple geometric treatment
6. explicit placeholder slot with required aspect ratio and art direction
7. generated asset only by explicit request

## Demo behavior

For a first-contact demo, visual polish must not depend on expensive asset generation.

If good temporary imagery exists publicly, reuse only the minimum needed and record provenance in `research/ASSET_MANIFEST.md`.

If no suitable imagery exists, design an intentional image-light layout or use clearly marked asset slots. Do not spend a long run generating substitute art.

## Refinement behavior

Prefer replacing temporary demo assets with client-owned/licensed assets.

Do not regenerate assets merely because discovery changed wording or layout.

## Asset manifest

When external or temporary assets are used, record:

- source
- owner/brand
- usage location
- temporary vs production-approved
- replacement needed: yes/no

Keep the manifest concise.

## Stop rule

If finding or creating an asset is taking longer than choosing a good placeholder/art-direction slot, stop and use the slot.
