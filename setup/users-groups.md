# Users & Groups (Step‑by‑Step)

> You already have users & groups — map them to this plan.

## 1) Groups
Create (or confirm) the following security groups:
- **Admins**
- **Executives**
- **Employees**

## 2) Users (Example Mapping)
- Add at least 1 user to **Admins** (lab admin account).
- Add 1–2 users to **Executives** (simulate sensitive accounts).
- Add 3–5 users to **Employees**.

> Use test mailboxes/usernames. **Do not** commit any PII in this repo.

## 3) Minimal Roles
- **Admins group** → Assign via **PIM** where possible:
  - `Privileged Role Administrator` *(eligible)* for role assignment tests.
  - `Security Reader` for KQL/log visibility.
- Avoid assigning **Global Administrator** broadly.

## 4) Verify MFA
- Enforce MFA via **Security defaults** or **Conditional Access** (see CA docs).
- Do at least one **successful MFA** sign-in per group to generate baseline logs.
