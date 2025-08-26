# Scenario 01 – Token Replay (Conceptual, Safe)

> **Objective**: Understand logs & controls around session/token misuse without performing theft.

## Steps (Generate Useful Logs)
1. Ensure at least one user in **Employees** has MFA enabled.
2. From two different networks (e.g., home Wi‑Fi and mobile hotspot), perform sign-ins within a short window.
3. In between sign-ins, trigger **Sign out of all sessions** for that user (Entra → Users → Select user → Sign-in logs → `Revoke sessions` or `Sign out of all sessions`).
4. Attempt another sign-in to observe re-authentication.

## What to Capture
- **SigninLogs** entries showing different IPs/devices and session resets.
- Notes on CA evaluation (was MFA required again? CAE in effect?).

## KQL to Run
- See `detections/kql/session_anomaly.kql` and adapt by UPN/time range.

## Mitigations to Document
- Enforce MFA, enable CAE, reduce token lifetimes as appropriate, monitor impossible travel and session anomalies.
