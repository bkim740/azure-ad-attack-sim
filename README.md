# Azure Entra ID Attack Simulation (Blue-Team Focus)

> **Purpose**: Show realistic **identity attack paths** in a *lab* tenant and how to **detect & mitigate** them.
> **Scope**: Safe, high-level simulations only — no exploit code or illegal activity.

## Attack Paths Simulated (Blue-Team Focus)

- **Password reset / session hijack** → Mitigated by MFA (Conditional Access)
- **Privilege abuse of executive accounts** → Scoped CA policy to "Executives" group
- **Bypass of Security Defaults** → Disabled defaults to show custom CA hardening
- **Sign-in monitoring** → Enforced MFA and verified via Sign-in logs

## Contents
- `setup/` – step-by-step lab preparation
- `scenarios/` – safe simulation guides to generate logs/evidence
- `detections/kql/` – KQL queries for AuditLogs/SigninLogs
- `mitigations/` – hardening guides & policy baselines
- `architecture/` – diagrams and policy matrix
- `report/` – executive summary & findings templates
- `evidence/` – put **sanitized** screenshots/log snippets here
- `push-to-github.md` – exact commands to publish this repo

## Quick Start
1. **Read** `setup/tenant-prereqs.md` and complete logging + permissions.
2. **Create/verify** users & groups per `setup/users-groups.md` (you can keep your own; just map them).
3. **Create two app registrations** (`setup/app-registrations.md`).
4. **Baseline hardening** (`mitigations/baseline-hardening.md`) and **Conditional Access** (`mitigations/ca-best-practices.md`).
5. **Run scenarios** in `scenarios/` to generate evidence.
6. **Run KQL** in `detections/kql/` to validate detections.
7. **Write-up** results in `report/` with screenshots under `evidence/`.
8. **Publish** with `push-to-github.md`.

## Ethics & Scope
- This repository is for **defensive education** in a **lab tenant** that you control.
- Never target production tenants or third parties. Redact all identifiers in evidence.
- No secrets/keys/tokens are stored in this repo.

## Evidence (Screenshots)

1. Reset password for Taylor Admin  
   ![01](evidence/screenshots/01_reset_password_taylor_admin.png)

2. First sign-in action required (MFA prompt)  
   ![02](evidence/screenshots/02_first_signin_action_required.png)

3. MFA QR code setup  
   ![03](evidence/screenshots/03_mfa_qr_code.png)

4. Admin Center overview (Taylor Admin)  
   ![04](evidence/screenshots/04_admin_center_overview.png)

5. Assign Entra ID P2 license  
   ![05](evidence/screenshots/05_assign_p2_license.png)

6. Disable Security Defaults  
   ![06](evidence/screenshots/06_disable_security_defaults.png)

7. Create Conditional Access policy (Executives MFA)  
   ![07](evidence/screenshots/07_create_ca_policy.png)

8. Policy in **Report-only** mode  
   ![08](evidence/screenshots/08_exec_policy_reportonly.png)

9. Policy **Enforced** (On)  
   ![09](evidence/screenshots/09_exec_policy_enforced.png)

10. Sign-in logs – **Report-only** evaluation  
    ![10](evidence/screenshots/10_signin_logs_reportonly.png)

11. Sign-in logs – **Enforced** (MFA required)  
    ![11](evidence/screenshots/11_signin_logs_enforced.png)

12. Lars CEO signed in (policy applied)  
    ![12](evidence/screenshots/12_lars_ceo_signedin.png)
