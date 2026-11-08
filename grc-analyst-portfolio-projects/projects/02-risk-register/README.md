# Project 2: Risk register for a mock company

[← Repository home](../../README.md)

## Objective

Act as the risk analyst for a 10-person cloud startup: identify at least 10 risks, score them by likelihood × impact, rate them, record mitigations and owners, and show the result as a heat map.

## Deliverables

| File | What it contains |
|---|---|
| [Risk register](risk-register.md) | 12 risks with scoring method, mitigation, owner, inherent, current and target residual risk, review dates and heat maps |
| [Risk summary report](risk-summary-report.md) | Half-page summary of the top three risks and recommended actions |
| [Heat map image](assets/risk-heat-maps.png) | Inherent, current and target heat maps |

## Key results

- **12 risks** from phishing and S3 misconfiguration to AI data leakage and key-person dependency.
- High risks fall from **3 inherent to 0 current**, and Low risks rise from 0 to 6 at target.
- Every risk links to ISO 27001 controls and has an owner and a review date.

## Improvements over the basic brief

- Added **current residual** and **target residual**, so the register shows what controls do today and what is still to be done, instead of assuming mitigations are finished.
- Wrote an explicit scoring scale with plain-language definitions.
- Used the same IDs and controls as [Project 1](../01-mini-compliance-program/README.md), so risks trace to controls.
- Added AI-specific risk (R-10), since the company's product depends on AI.

## Skills shown

Risk scoring · Risk treatment · Reporting · Heat map design · ISO 31000 and NIST RMF concepts

## Resume line

> Built a 12-risk register with a 5×5 scoring model, inherent, current and target residual ratings and heat maps; showed High risks falling from 3 to 0 with existing controls and Low risks rising to 6 at target.

---

*NovaCloud AI Solutions is a fictional company. All people, systems, incidents, ratings and dates are examples created for skills practice and portfolio use. This is not legal advice or a compliance determination. Framework references are paraphrased pointers, so verify them against the source text before relying on them.*

Author: Augustine Ozor, AI Governance and Cybersecurity GRC. [GitHub](https://github.com/AugustineOzor) · [LinkedIn](https://www.linkedin.com/in/augustinetettehozor)
