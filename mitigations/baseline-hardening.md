# Baseline Hardening (Step‑by‑Step)

## 1) MFA Everywhere
- Keep **Security defaults** ON *or* enforce MFA via **Conditional Access** for *All users*.
- Require MFA for roles under **Admins** and **Executives** explicitly.

## 2) Block Legacy Authentication
- Entra admin center → **Protection** → **Authentication methods** → disable legacy where applicable.
- Add a CA policy to **Block legacy auth clients**.

## 3) Admin Consent Workflow
1. Entra admin center → **Identity** → **Applications** → **Consent and permissions**.
2. Enable **Admin consent requests**.
3. Assign reviewers (your lab admin).
4. Test a user consent — ensure it generates a request (see scenario 04).

## 4) Conditional Access Baseline
- Policy 1: **Require MFA for all cloud apps** (exclude break-glass).
- Policy 2: **Block legacy authentication**.
- Optional: **Require device compliance** for Admins/Executives in enforced mode.

> Keep early CA policies in **Report-only** to capture logs, then **Enforce** and capture the “after”.
