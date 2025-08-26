# Logging Configuration (Detailed)

## Entra → Log Analytics
1. Entra admin center → **Identity** → **Monitoring & health** → **Diagnostic settings**.
2. `+ Add diagnostic setting` → Name `entra-to-law`.
3. Categories: **AuditLogs**, **SigninLogs** (and others if desired).
4. Destination: **Log Analytics** → choose your workspace.
5. Save and wait 5–15 min.

## Validate with KQL
- `SigninLogs | summarize count() by ResultType`
- `AuditLogs | summarize count() by OperationName | top 20 by count_ desc`

## CSV Exports (No LAW)
- Sign-in logs → **Download** → CSV
- Audit logs → **Download** → CSV
- Store under `evidence/` with redaction.
