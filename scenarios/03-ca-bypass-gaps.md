# Scenario 03 – Conditional Access Gaps (Safe)

> **Objective**: Use **Report‑only** CA to observe gaps, then enforce and verify closure.

## Steps
1. Create CA policy **Require MFA for Executives** in **Report‑only** mode.
2. Sign in as an **Executive** user and complete normal flow.
3. Review **Sign‑in logs** → policy evaluation → note **ConditionalAccessStatus** = `reportOnly`.
4. Switch CA policy to **On** (enforce). Sign in again and confirm **success** with MFA.
5. Create a second policy **Block legacy authentication** → Report‑only, generate a basic/legacy sign-in (if available) or review reports, then enforce.

## What to Capture
- Before/After screenshots from sign‑in logs showing CA evaluation results.
- Policy configuration (summary view).

## KQL
- `detections/kql/ca_not_applied.kql`

## Mitigations
- Remove broad **exclusions**; keep CA enforced for sensitive groups; block legacy auth.
