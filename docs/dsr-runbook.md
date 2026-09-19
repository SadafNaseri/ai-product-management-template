# GDPR Data Subject Request (DSR) Runbook · Juno

**Owner:** Product PM (Juno) · **SLA:** acknowledge within 72h, resolve within 30 days.

## Scope
Handles access, rectification, and erasure requests for any personal data Juno
processes (customer names, contact details) surfaced from Teams Channels, Jira, or the KB.

## Steps
1. Receive DSR via the privacy intake channel; log request ID and timestamp.
2. Verify requester identity before any data is retrieved.
3. Locate all Juno-held data for the subject (working memory, logs, cached outputs).
4. Action the request (export / correct / delete) and record what changed.
5. Confirm completion to the requester; close the log entry with resolution date.

## Notes
- PII is scrubbed pre-LLM, so persistent stores should hold minimal personal data by design.
- Erasure includes eval logs and cached top-3 outputs, not just live context.
