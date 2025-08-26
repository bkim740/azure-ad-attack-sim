# Scenario 04 – Consent Phishing (OAuth) – Governance Demo

> **Objective**: Demonstrate governance by requiring **Admin consent** and reviewing consent requests.

## Steps
1. Enable **Admin consent workflow** (see mitigations).
2. While signed in as a normal **Employee** user, in `AppB-Risky` try to **request** consent for a permission that requires admin approval.
3. Review the **Admin consent requests** queue as the reviewer; **Deny** with justification.
4. Observe **AuditLogs** events of the request and decision.

## What to Capture
- Screenshots of the request and the admin decision.
- Audit logs entries with timestamps.

## Mitigations
- Keep user consent restricted; enforce publisher verification for third‑party apps; review new consented apps regularly.
