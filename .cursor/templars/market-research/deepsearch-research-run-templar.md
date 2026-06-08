---
id: templar.market-research.deepsearch-research-run.v1
kind: templar
version: 1.0.0
description: Internal research-run artifact — normalized subject, query plan, sources, deduped evidence with timestamps and traceability fields
globs: ""
governs: ""
implements: market-research.deepsearch.research-run-artifact
requires: []
model_hints: { temp: 0.2, top_p: 0.9 }
provenance: { owner: team-market-research, last_review: 2026-06-02 }
---

# Research run artifact (JSON shape)

Emit as JSON (or equivalent structured store). Replace `{{PLACEHOLDERS}}` with concrete values; extend arrays as needed.

```json
{
  "subject": {
    "canonical": "{{SUBJECT_CANONICAL}}",
    "aliases": ["{{ALIAS_1}}"],
    "excludedHomonyms": ["{{HOMONYM_EXCLUSION}}"]
  },
  "goal": "{{RESEARCH_GOAL}}",
  "sourcePolicy": {
    "families": ["{{SOURCE_FAMILY_1}}"],
    "defaultsDocumented": true
  },
  "queryPlan": {
    "families": ["{{QUERY_FAMILY_1}}"],
    "notes": "{{QUERY_PLAN_NOTES}}"
  },
  "sources": [
    {
      "connectorId": "{{CONNECTOR_ID}}",
      "family": "{{SOURCE_FAMILY}}",
      "enabled": true
    }
  ],
  "rawHits": [
    {
      "url": "https://example.com/page",
      "retrievedAt": "{{ISO8601Z}}",
      "connectorId": "{{CONNECTOR_ID}}"
    }
  ],
  "evidence": [
    {
      "id": "E-1",
      "url": "https://example.com/evidence",
      "canonicalUrl": "https://example.com/evidence",
      "retrievedAt": "{{ISO8601Z}}",
      "publishedAt": null,
      "updatedAt": null,
      "snippet": "{{SHORT_SNIPPET_OR_POINTER}}",
      "connectorId": "{{CONNECTOR_ID}}"
    }
  ],
  "dedupeNotes": "{{DEDUPE_OR_FAILURE_LOG_SUMMARY}}"
}
```

Minimum fields per `rule.market-research.deepsearch.contract.v1`: `subject`, `goal`, `sources[]`, `evidence[]` with `url`, `retrievedAt`, `publishedAt` (nullable), `snippet` or content pointer.

---

`Research-run: subject={{SUBJECT_CANONICAL}} | connectors={{CONNECTOR_LIST}} | contract=rule.market-research.deepsearch.contract.v1 | ts={{ISO8601Z}}`
