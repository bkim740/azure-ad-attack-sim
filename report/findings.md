# Findings & Evidence

## F‑01: Admin Consent Granted to Risky App
- **What we did:** Granted `Directory.Read.All` to `AppB-Risky` (lab only), then removed.
- **Evidence:** AuditLogs → `Add app role assignment to service principal` (timestamp …).
- **Risk:** Over‑privileged apps can harvest directory data.
- **Mitigation:** Admin consent workflow; least privilege; periodic reviews.

## F‑02: CA Policy in Report‑Only Allowed Access
- **What we saw:** `ConditionalAccessStatus = reportOnly` allowed successful sign‑in without enforcement.
- **Mitigation:** Enforce policy after validation; remove wide exclusions.

## F‑03: Consent Request Blocked via Workflow
- **What we saw:** Employee request denied by reviewer; logged in AuditLogs.
- **Mitigation:** Keep user consent restricted; require publisher verification.
