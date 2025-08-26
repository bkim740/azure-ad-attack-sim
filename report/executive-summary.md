# Executive Summary

**Objective.** Demonstrate identity attack paths in an Entra ID lab and validate detections/mitigations.

**Key Findings.**
- Over‑privileged applications can silently gain broad directory visibility.
- Conditional Access in `report-only` mode provides no protection; enforcing policies closes gaps.
- Consent governance prevents risky third‑party app access.

**Recommendations.**
- Enforce MFA and block legacy auth for all users.
- Implement admin consent workflow and review service principals in directory roles.
- Monitor Audit/Sign‑in logs with scheduled KQL queries and alerts.

*(Attach sanitized screenshots in `evidence/`)*
