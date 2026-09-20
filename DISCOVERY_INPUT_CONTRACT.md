# Discovery Input Contract

The default discovery source is `client-brief.json` exported by `Terraciano/discovery-console`.

Current schema version: `1`.

## Required top-level fields

Expected shape:

```json
{
  "schemaVersion": 1,
  "project": {
    "brandName": "",
    "demoRepository": "owner/repo",
    "demoUrl": "",
    "realBusiness": "",
    "industry": "",
    "subcategory": "",
    "geography": ""
  },
  "business": {},
  "audience": {},
  "brand": {},
  "trust": {},
  "website": {},
  "content": {},
  "operations": {},
  "constraints": {},
  "evidence": {
    "confirmedFacts": [],
    "inferences": [],
    "unknowns": []
  },
  "refinement": {
    "mode": "refine-existing-demo",
    "instruction": ""
  }
}
```

## Validation rules

Before use:

1. `schemaVersion` must be supported.
2. `project.demoRepository` must identify the demo repo.
3. `refinement.mode` must equal `refine-existing-demo` for post-discovery refinement.
4. evidence arrays must exist.
5. empty sections are allowed.
6. empty values are not facts.
7. unknowns must remain unknown unless independently resolved.

If the payload is partially complete, proceed with the known facts and explicitly record remaining gaps.

## Field semantics

### project
Identity and target repo.

### business
What is sold, commercial model, differentiators, transaction context.

### audience
Primary buyer, sophistication, objections, gatekeepers, relationship context.

### brand
Story, identity, perception, vocabulary, likes/dislikes, preservation constraints.

### trust
Only proof the client says can be used.

### website
Goal, CTA, sections, demo feedback, integrations, language requirements.

### content
Available brand assets, photography, video, copy, document sources.

### operations
Domain, DNS, inquiry routing, analytics, legal, ownership, launch constraints.

### constraints
Non-negotiables, out-of-scope items, open questions, internal refinement notes.

## Safety around proof

A non-empty trust field is not automatically approved proof unless its corresponding discovery answer is confirmed.

Treat inferred trust items as leads to verify, not publishable claims.

## Compatibility rule

Future schema versions must be explicitly supported before use.

Do not silently reinterpret unknown schema versions.
