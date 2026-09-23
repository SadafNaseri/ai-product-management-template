# Juno PM — AI Copilot for RocketShip’s Product Org

> An AI Associate PM that turns Teams Channels/Confluence/Jira chaos into a prioritised top-3 risk list every morning.

_Sadaf Naseri · AI PM Cohort · Sep 2026_

Repo: https://github.com/SadafNaseri/ai-product-management-template

This repo is my final project for the AI Product Management Certification — **Juno PM**. Each module’s artefact lives in its own folder; this README is the dashboard and the pitch.

---

## Module artefacts

### M1 · Prompting
- **System prompt** — [`01-prompting/system-prompt.md`](01-prompting/system-prompt.md)
- **Prototype** — https://sn-rocketship-insight-flow.lovable.app

### M2 · Strategy
- **Decision matrix** — [`02-strategy/decision-matrix.md`](02-strategy/decision-matrix.md)
- **AI Strategy one-pager** — [`02-strategy/strategy-one-pager.md`](02-strategy/strategy-one-pager.md)

### M3 · RAG / AI PRD
- **AI PRD** — [`03-rag-prd/prd.md`](03-rag-prd/prd.md)

### M4 · AI-Native UX
- **AI user flow** — [`04-ai-ux/user-flow.md`](04-ai-ux/user-flow.md)
- **Trust-gap mitigations** — [`04-ai-ux/trust-gaps.md`](04-ai-ux/trust-gaps.md)

### M5 · Agentic Workflows
- **Agent Workflow Spec (AWSpec)** — [`05-agentic-workflows/awspec.md`](05-agentic-workflows/awspec.md)
- **Agent Control Panel** — [`05-agentic-workflows/agent-control-panel.md`](05-agentic-workflows/agent-control-panel.md)

### M6 · Evals &amp; Guardrails
- **Eval stack** — [`06-evals/eval-stack.md`](06-evals/eval-stack.md)
- **Human evaluation rubric** — [`06-evals/human-rubric.md`](06-evals/human-rubric.md)

---

## PM Execution Plan

### Where Juno is today
- All six modules specced, committed, and now internally consistent: one autonomy stance (Copilot, no auto-publish), one confidence-tier definition, and red lines that map to real gates.
- Prototype validates the RAG + tool-trace flow with the team; every priority is grounded and shows its audit trail.
- Automated evals: golden-set schema and format defined in 06-evals/golden-set/ with representative samples; curation toward the 200-item target in progress; judge prompt drafted, validation pending against the curated set; not yet wired to CI.
- Human rubric drafted; 2 graders lined up; no live calibration round yet.

### What ships next (next 2 sprints)
- Sprint 1: attack the named bottleneck. Tighten retrieval/chunking and the verbatim-citation gate against the golden set; wire the eval harness to CI; run the first grader calibration round.
- Sprint 2: closed beta with 3 PMs (1 RocketShip, 2 customers); instrument the strategy outcome metrics below; weekly rubric review.

### What I watch (dashboards)
- Strategy outcomes (the M2 targets): weekly prioritization cycle time (target 2h -> 30min); decision-reversal rate within 1 week (target < 10%); share of priorities with 2+ cited sources (target 90%+).
- Product health (daily): thumbs-down rate, regen rate, hand-off rate.
- Eval health (per release): golden-set accuracy; format/citation/refusal pass rate; cost per run.

### Red lines (what blocks shipping)
- Any critical-safety fail (any "1" on safety dimension in human eval).
- <90% golden-set accuracy on automated layer.
- Customer-name fabrication in last 30 days.
- Cost >$0.50 per run (hard ceiling; operating target $0.12/run per M3).
- P95 latency >8s on triage flow.

### Governance
- Compliance: PII scrubber pre-LLM; GDPR DSR handler in /docs/dsr-runbook.md.
- Safety: prompt-injection eval row in golden set; refusal on legal/contract content.
- Reliability: 99.5% SLO; cached top-3 fallback if model is down.
- Reputation: 2-hour incident-response playbook in /docs/incident-response-playbook.md; canary deploys for every model swap.

---

## Build Insights

- **Friction point.** Grounding is only as trustworthy as retrieval. A confident priority built on a weak chunk still reads as authoritative, which makes it the most dangerous failure mode, so chunking strategy and the verbatim-citation gate mattered more than the choice of model.
- **Key learning.** Autonomy is a strategy decision, not an engineering one. "Copilot" was declared in M2, but the agent spec had quietly drifted to auto-publish by M5. A single wrong auto-post would have burned the leadership trust the whole product depends on, so holding every module to draft-then-approve is what keeps the promise credible.
- **Aha moment.** A red line is theatre until it is a gate. The cost, latency, and safety limits only became real once each one mapped to an enforcement point in the eval stack and the control panel. A stated limit with no enforcement hook is just a wish.


---

_Certification submission — AI Product Management Certification._
