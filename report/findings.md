# Findings & Evidence

---

## F-01: Password Reset / Session Hijack

- **What we did:** Reset password for *Taylor Admin* and observed first sign-in MFA requirement.  
- **Evidence:**  
  - [01_reset_password_taylor_admin.png](../evidence/screenshots/01_reset_password_taylor_admin.png)  
  - [02_first_signin_action_required.png](../evidence/screenshots/02_first_signin_action_required.png)  
  - [03_mfa_qr_code.png](../evidence/screenshots/03_mfa_qr_code.png)  
- **Risk:** Compromised credentials without MFA could allow hijacked sessions.  
- **Mitigation:** Require MFA for all privileged users; enforce conditional access at first login.  

---

## F-02: Privilege Abuse of Executive Accounts

- **What we did:** Assigned Entra ID P2 license and created a Conditional Access (CA) policy scoped to the *Executives* group.  
- **Evidence:**  
  - [04_admin_center_overview.png](../evidence/screenshots/04_admin_center_overview.png)  
  - [05_assign_p2_license.png](../evidence/screenshots/05_assign_p2_license.png)  
  - [07_create_ca_policy.png](../evidence/screenshots/07_create_ca_policy.png)  
- **Risk:** Executives are prime phishing/credential theft targets. Without scoped CA enforcement, attackers can escalate privileges.  
- **Mitigation:** Apply least privilege, enforce MFA for executives, and monitor sign-in activity closely.  

---

## F-03: Bypass of Security Defaults

- **What we did:** Disabled Microsoft Security Defaults to simulate weaker baseline protection.  
- **Evidence:**  
  - [06_disable_security_defaults.png](../evidence/screenshots/06_disable_security_defaults.png)  
- **Risk:** Without security defaults, accounts are exposed to password spray, phishing, and brute-force attacks.  
- **Mitigation:** Replace defaults with custom Conditional Access baselines tailored to org needs.  

---

## F-04: Sign-In Monitoring (Report-Only vs Enforced)

- **What we did:** Tested Conditional Access in *Report-only* mode and then enforced it. Verified logs for both states.  
- **Evidence:**  
  - [08_exec_policy_reportonly.png](../evidence/screenshots/08_exec_policy_reportonly.png)  
  - [09_exec_policy_enforced.png](../evidence/screenshots/09_exec_policy_enforced.png)  
  - [10_signin_logs_reportonly.png](../evidence/screenshots/10_signin_logs_reportonly.png)  
  - [11_signin_logs_enforced.png](../evidence/screenshots/11_signin_logs_enforced.png)  
- **Risk:** Report-only mode shows gaps where users could bypass MFA enforcement.  
- **Mitigation:** Move policies from report-only to enforced once validated; continuously monitor sign-in logs.  

---

## F-05: Policy Enforcement Validated (Executive Sign-In)

- **What we did:** Signed in as *Lars CEO* after CA policy enforcement. MFA prompt and sign-in were enforced successfully.  
- **Evidence:**  
  - [12_lars_ceo_signedin.png](../evidence/screenshots/12_lars_ceo_signedin.png)  
- **Risk:** Without enforced MFA, high-value accounts remain vulnerable to takeover.  
- **Mitigation:** Keep executive accounts under enforced Conditional Access and verify via continuous log review.  

