---
name: extract-brand-baseline
description: Extract the prospect's existing visual identity from first-party public sources before designing a first-contact demo. Use in generate mode whenever the prospect already has a website or other first-party digital presence.
---

# Brand baseline extraction

This is a preservation step, not a redesign step.

If the prospect has a current first-party website, inspect it before competitor or visual-reference research.

## Inspect

Prioritize:
1. homepage HTML and linked stylesheets
2. global CSS variables / design tokens
3. computed-looking recurring values visible in source CSS
4. font declarations and loaded font families
5. logo variants and wordmark treatment
6. header/navigation treatment
7. buttons/links/accent behavior
8. backgrounds, borders, radii, spacing, container widths
9. image treatment / crops / overlays
10. recurring motion patterns only if clearly part of identity

Do not crawl the entire site.

Default limit:
- homepage
- one representative product/service page
- global stylesheet(s)
- one brand/about page only if needed

## Output

Create:

`research/BRAND_BASELINE.md`

Keep it concise.

Required sections:

### Sources
First-party URLs/files inspected.

### Brand colors
For each recurring color:
- value
- observed role
- confidence: high / medium / low

Separate:
- core brand color
- accent
- text
- surface/background
- utility/status colors

Do not promote a one-off campaign/status color into the brand palette.

### Typography
Capture:
- font families
- display/body roles
- weight patterns
- capitalization/tracking cues

If font identity cannot be confirmed, say unknown.

### Logo / marks
Describe:
- available variants
- dominant lockup
- light/dark usage
- spacing/background behavior

Do not redraw or invent a logo.

### Shape / UI cues
Capture only recurring cues:
- radii
- borders
- button shape
- separators
- container geometry
- navigation treatment

### Media language
Capture:
- photography subject
- crop behavior
- color grading
- illustration/icon style
- overlays

### Preserve
List identity cues the demo should keep.

### Safe to reinterpret
List presentation details that can change without changing identity.

### Unknown
List unresolved brand facts.

## Decision rule

Existing first-party branding outranks:
- industry defaults
- competitor palettes
- aesthetic preference
- generic “premium” palettes

Never invent a new accent color merely to make the design feel more interesting.

A new color is allowed only if:
1. the existing brand genuinely has no usable accent/system, and
2. `DESIGN_DIRECTION.md` explains why it is needed, and
3. it does not conflict with first-party identity.

## Token discipline

Do not paste full CSS files.

Extract only:
- meaningful variables
- repeated hex/rgb/hsl values
- font declarations
- a few representative component rules

The objective is a compact brand model, not a stylesheet transcript.
