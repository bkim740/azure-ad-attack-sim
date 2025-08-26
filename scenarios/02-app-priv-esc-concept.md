# Scenario 02 – App-Based Privilege Escalation (Conceptual)

> **Objective**: Show why over‑privileged apps or role‑assigned service principals are risky (in lab only).

## Steps (Audit Evidence Only)
1. Using **AppB-Risky**, request **Directory.Read.All** (application) and **User.Read** (delegated).
2. As a lab admin, click **Grant admin consent** and record the action.
3. (Optional) Assign the service principal of `AppB-Risky` to **User Administrator** *temporarily*.
4. Remove the role and any unneeded permissions after screenshots.

## What to Capture
- **AuditLogs** entries for:
  - `Add app role assignment to service principal`
  - `Add member to role` (target type service principal)
- Screenshots of API permissions page (sanitized).

## KQL to Run
- `detections/kql/app_high_perms.kql`
- `detections/kql/sp_role_added.kql`

## Mitigations
- Least privilege; admin consent workflow; periodic review of service principals in directory roles.
