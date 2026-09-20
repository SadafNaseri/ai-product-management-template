# Golden Set · Juno P0 Triage

Curated evaluation set for the automated eval layer (see ../eval-stack.md).

## What this is
Anonymised P0 escalation threads paired with the PM-curated "correct" top-3 risk list. The LLM-as-judge and code-based layers score model output against these on every PR and nightly, for accuracy, citation grounding, format, and refusal.

## Status
- Target size: 200 anonymised P0 threads.
- Current: <SET TO YOUR REAL COUNT> curated; judge prompt validated against 30 items.
- Representative format samples live in `sample-entries.jsonl`.

## Entry schema (one JSON object per line, JSONL)
- `id`: stable identifier (e.g. gs-0001)
- `thread`: array of messages, each `{ idx, author_role, text }`
- `expected_top_3`: array of `{ rank, risk, customer_signal, source_idx, strategic_pillar, suggested_action, confidence }`
- `notes`: curator rationale for the expected ranking

`source_idx` references a message `idx` in `thread`, so citation grounding is checkable automatically.

## Rules
- Course scenario uses the fictional RocketShip entities. When productionised, anonymise real data: no real customer names, ARR, contract terms, or PII before commit.
- Every expected risk must cite at least one `source_idx` that exists in the thread.
- Out-of-scope items (per the strategy decision rules) must NOT appear in expected_top_3.

## Versioning
- Changes go through PR review (a golden-set edit can move the accuracy bar).
- Record the set version used for each release in the eval run log.
- Refresh quarterly and after every major incident.
