---
id: templar.market-research.deepsearch-pack.v1
kind: templar
version: 1.0.0
description: User-facing deepsearch delivery pack — executive tie-in, recency-ranked findings, goal relevance, economics, key people, outreach intelligence, limitations
globs: ""
governs: ""
implements: market-research.deepsearch.pack
requires: []
model_hints: { temp: 0.2, top_p: 0.9 }
provenance: { owner: team-market-research, last_review: 2026-06-02 }
---

# Deepsearch pack — {{SUBJECT_CANONICAL}}

**Research goal**: {{RESEARCH_GOAL}}  
**Recency policy**: {{RECENCY_POLICY}}  
**Goal facets**: {{GOAL_FACETS}}

## Executive tie-in

| Bullet | Tag (`fact` / `inference` / `hypothesis`) | Evidence ids |
|--------|-------------------------------------------|--------------|
| {{EXEC_BULLET_1}} | | |
| {{EXEC_BULLET_2}} | | |

## Recency-ranked findings

Sorted by **effective date** (newest first within quality gates). Quality = authority × corroboration × independence × facet match × recency decay (not freshness alone).

| Id | Effective date | Title / claim | Quality score | Facet match | Notes |
|----|------------------|---------------|---------------|-------------|-------|
| E-… | | | | | |

## Relevance to goal

| Finding (id) | Implication for goal |
|--------------|----------------------|
| | |

## Economics & business model

### Customer & value proposition

{{ECON_CUSTOMER}} — Evidence: {{EVIDENCE_IDS}} or `unknown`

### Revenue mechanics & pricing signals

{{ECON_REVENUE}} — Evidence: … or `unknown`

### Distribution & go-to-market

{{ECON_DISTRIBUTION}} — Evidence: … or `unknown`

### Suppliers, partners, ecosystem

{{ECON_PARTNERS}} — Evidence: … or `unknown`

### Defensibility / moats

{{ECON_MOATS}} — Evidence: … or `unknown`

## Key people & orgs

| Name / org | Role | Why it matters (goal-linked) | Influence signals (public, ToS-compliant) |
|------------|------|------------------------------|---------------------------------------------|
| | | | |

## Outreach & social intelligence

### Channel inventory

{{CHANNEL_LIST}}

### Example posts (public permalinks only)

| url | platform | date (if shown) | ≤25-word excerpt | pattern tags |
|-----|----------|-----------------|------------------|--------------|
| | | | | |

### Pattern analysis

{{SOCIAL_PATTERNS}}

### Do better (ethical — patterns, not impersonation)

{{DO_BETTER_RECOMMENDATIONS}}

## Limitations

{{COVERAGE_GAPS}}

---

`Delivery: rule.market-research.deepsearch.delivery.v1 | goal-facets={{GOAL_FACETS}} | recency-policy={{RECENCY_POLICY}} | ts={{ISO8601Z}}`
