# Tenant Prerequisites (Step‑by‑Step)

> Goal: Ensure you can **log**, **query**, and **audit** everything you do in the lab.

## 1) Confirm Admin Access
1. Go to **Entra admin center** → **Identity**.
2. Ensure you have a dedicated **Global Administrator** or **Privileged Role Administrator** account for *lab*.
3. For daily work, prefer a normal account + elevation via **PIM** (if available).

## 2) Create a Log Analytics Workspace (optional but recommended)
1. Azure Portal → **Log Analytics workspaces** → **Create**.
2. Name: `entra-lab-logs` (any region close to you).

## 3) Stream Entra ID Logs to Log Analytics
1. Entra admin center → **Identity** → **Monitoring & health** → **Diagnostic settings** (or "Export Settings").
2. Create a diagnostic setting:
   - Name: `entra-to-law`
   - **Categories**: enable **AuditLogs**, **SigninLogs** (and **ProvisioningLogs** if using SCIM).
   - Destination: **Send to Log Analytics** → select the workspace created above.
3. Save. Wait ~5–15 minutes and generate some sign-ins to validate.

## 4) Validate Logs
1. Azure Portal → **Log Analytics workspaces** → your workspace → **Logs**.
2. Run:
```kql
SigninLogs | take 5
```
and
```kql
AuditLogs | take 5
```
3. You should see recent rows. If not, revisit the diagnostic setting.

## 5) Security Defaults vs Conditional Access
- If **Security defaults** are ON, either:
  - Keep them for a baseline and add CA in **report-only** mode temporarily for evaluation, or
  - Turn them OFF (only if you enforce equivalent CA policies) to avoid conflicts.
- Document what you chose in `mitigations/baseline-hardening.md`.

## 6) Export Alternative (No Log Analytics)
- You can export CSVs from **Sign-in logs** and **Audit logs** for screenshots and attach to `evidence/`.
- If you skip Log Analytics, still keep the KQL files in this repo to demonstrate capability.
