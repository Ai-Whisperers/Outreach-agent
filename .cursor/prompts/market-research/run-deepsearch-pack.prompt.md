---
name: run-deepsearch-pack
description: "Produce a contract-aligned research artifact and a delivery deepsearch pack from a subject and goal"
category: market-research
tags: market-research, deepsearch, research, intelligence, synthesis
argument-hint: "Subject (brand/product/service/niche) and research goal"
---

# Run deepsearch pack

Use when the user wants **discovery plus a structured delivery pack** (recency-ranked findings, goal relevance, economics, key people, ethical outreach intelligence).

## Rules (load and follow)

1. `rule.market-research.deepsearch.contract.v1` — subject normalization, query plan, evidence, dedupe, traceability.
2. `rule.market-research.deepsearch.delivery.v1` — ranking, facets, economics, people, social intel, limitations.
3. `rule.general.verify-info.v1` — no unsupported factual claims.

Invocation map: `rule.market-research.agent-application.v1`.

## Templars (shape outputs)

1. **Internal artifact**: `.cursor/templars/market-research/deepsearch-research-run-templar.md` (`templar.market-research.deepsearch-research-run.v1`) — JSON-shaped run with `evidence[]` and timestamps before synthesis.
2. **User-facing pack**: `.cursor/templars/market-research/deepsearch-pack-templar.md` (`templar.market-research.deepsearch-pack.v1`) — final Markdown sections and provenance footer.

## Required context

```xml
<deepsearch>
  <subject>{{SUBJECT}}</subject>
  <goal>{{RESEARCH_GOAL}}</goal>
  <recencyPolicy optional="true">{{RECENCY_POLICY}}</recencyPolicy>
  <sourcePolicy optional="true">{{SOURCE_FAMILIES}}</sourcePolicy>
</deepsearch>
```

## Steps

1. Normalize subject and state disambiguation; if ambiguous, ask or present top candidates.
2. Emit the **research-run** structure (from templar 1) populated with real evidence ids and dates where available; mark unknown dates.
3. Apply delivery steps: goal facets, effective dates, composite scoring, economics/people/social sections per rule.
4. Emit the **pack** (from templar 2) with every executive bullet tagged `fact` / `inference` / `hypothesis` and evidence pointers.
5. Append both provenance footers from the templars.

If the user only wants discovery breadth without a full pack, still use the contract templar and stop before the pack templar unless they ask for the full delivery.
