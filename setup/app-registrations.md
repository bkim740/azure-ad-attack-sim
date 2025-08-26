# App Registrations (Step‑by‑Step)

Create two apps to demonstrate good vs risky patterns. **No secrets/IDs in repo.**

## App A – "Well‑Configured"
1. Entra admin center → **Applications** → **App registrations** → **New registration**.
2. Name: `AppA-WellConfigured`
3. Supported account types: **Single tenant**.
4. Redirect URI: leave empty (for this demo).
5. After creation → **API permissions**:
   - Add **Microsoft Graph** → **Application permissions** → e.g., `User.Read.All` (admin consent required).
   - Click **Grant admin consent** (document this action).
6. **Certificates & secrets**: *Skip* (or create a short-lived secret for demo and delete after screenshots).

## App B – "Risky Configuration" (Lab Only)
1. Create another app: `AppB-Risky`
2. Supported account types: **Multitenant** (demonstrates broader exposure).
3. API permissions:
   - Add Graph **Application permissions** such as `Directory.Read.All` and at least one **delegated** scope.
   - **Do not** grant wild, unnecessary scopes in real life; this is for audit-log evidence only.
4. (Optional demo) Add the **service principal** of `AppB-Risky` to a directory role like **User Administrator** using a lab admin account. *Document & remove afterward*.

## Evidence to Capture
- Screenshots of **API permissions** page (with UPNs redacted).
- **AuditLogs** entries for:
  - Admin consent granted
  - App role assignment to service principal
  - Role membership changes

> Remove high privileges and secrets after recording evidence.
