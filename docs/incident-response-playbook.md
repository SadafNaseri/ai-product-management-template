# Incident Response Playbook · Juno

**Response commitment:** first human response within 2 hours of a Sev-1/Sev-2 alert.
**Owner:** on-call PM + Eng on-call.

## Severity
- **Sev-1:** customer-name fabrication, PII leak, or wrong priority auto-surfaced.
- **Sev-2:** degraded retrieval or eval gate breach; no external exposure.

## Steps
1. Detect: alert fires (eval gate fail, thumbs-down cluster, or manual report).
2. Triage: assign severity; page on-call PM for Sev-1.
3. Mitigate: disable auto-surfacing, fall back to cached top-3, or take Juno offline.
4. Communicate: notify affected PMs; log timeline.
5. Postmortem: blameless writeup within 5 business days; add a golden-set eval row for the failure mode.

## Notes
- Every model swap ships as a canary deploy; roll back on any Sev-1.
