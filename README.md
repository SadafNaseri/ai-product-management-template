# Juno PM — AI Copilot for RocketShip’s Product Org

> An AI Associate PM that turns Teams Channels/Confluence/Jira chaos into a prioritised top-3 risk list every morning.

_Sadaf Naseri · AI PM Cohort · Sep 2026_

Repo: https://sn-rocketship-insight-flow.lovable.app

This repo is my final project for the AI Product Management Certification — **Juno PM**. Each module’s artefact lives in its own folder; this README is the dashboard and the pitch.

---

## Module artefacts

### M1 · Prompting
- **System prompt** — [`01-prompting/system-prompt.md`](01-prompting/system-prompt.md)
- **Prototype** — https://sn-rocketship-insight-flow.lovable.app

### M2 · Strategy
- **Decision matrix** — [`02-strategy/decision-matrix.md`](02-strategy/decision-matrix.md)
- **AI Strategy one-pager** — [`strategy-one-pager.md`](strategy-one-pager.md)

### M3 · RAG / AI PRD
- **AI PRD** — [`prd.md`](prd.md)

### M4 · AI-Native UX
- **AI user flow** — [`user-flow.md`](user-flow.md)
- **Trust-gap mitigations** — [`trust-gaps.md`](trust-gaps.md)

### M5 · Agentic Workflows
- **Agent Workflow Spec (AWSpec)** — [`awspec.md`](awspec.md)
- **Agent Control Panel** — [`agent-control-panel.md`](agent-control-panel.md)

### M6 · Evals &amp; Guardrails
- **Eval stack** — [`eval-stack.md`](eval-stack.md)
- **Human evaluation rubric** — [`human-rubric.md`](human-rubric.md)

---

## PM Execution Plan

### Where Juno is today
- M1–M6 specced and committed.
- The prototype validates the M1 flow with the team.
- Automated evals: 200-item golden set drafted, judge prompt validated against 30 items; not yet wired to CI.
- Human rubric drafted; 2 grader candidates lined up; no calibration round yet.

### What ships next (next 2 sprints)
- Sprint 1: wire the eval harness to CI; staff and calibrate 2 graders; ship the Team Channel triage tool.
- Sprint 2: open closed beta with 3 PMs (1 RocketShip, 2 customers); weekly rubric review; instrument abandon-rate.

### What I watch (dashboards)
- Daily: thumbs-down rate, regen rate, hand-off rate.
- Weekly: human-rubric mean per dimension; refusal hit-rate; cost per run.
- Per release: golden-set accuracy; format/citation/refusal pass rate.

### Red lines (what blocks shipping)
- Any critical-safety fail (any "1" on safety dimension in human eval).
- <90% golden-set accuracy on automated layer.
- Customer-name fabrication in last 30 days.
- Cost >$0.50 per run.
- P99 latency >5s on triage flow.

### Governance
- Compliance: PII scrubber pre-LLM; GDPR DSR handler in /docs/dsr-runbook.md.
- Safety: prompt-injection eval row in golden set; refusal on legal/contract content.
- Reliability: 99.5% SLO; cached top-3 fallback if model is down.
- Reputation: 2-hour incident-response playbook in /docs; canary deploys for every model swap.

---

## Build Insights

- **Friction point.** Retrieval quality was the bottleneck — chunking strategy mattered more than the model.
- **Key learning.** Eval rubrics force the product decisions that PRDs let you hide.
- **Aha moment.** The system prompt is the product — the UI is the wrapper.

---

_Certification submission — AI Product Management Certification._
