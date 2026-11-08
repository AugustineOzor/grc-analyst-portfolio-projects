# Vendor risk scorecard

[← Project 3 README](README.md)

## Criticality ranking of all 12 vendors

Each vendor is scored on data sensitivity, business dependency and access level (1 to 3 each), using the [template](vendor-questionnaire-template.md). The ranking sets the order in which vendors are assessed.

| Rank | Vendor | Asset | Data | Dependency | Access | Score | Tier | Assessed? |
|---|---|---|---|---|---|---|---|---|
| 1 | AWS | AST-01 to AST-05 | 3 | 3 | 3 | 9 | Critical | No |
| 2 | GitHub | AST-09 | 3 | 3 | 2 | 8 | Critical | No |
| 3 | Google Workspace | AST-10 | 3 | 3 | 2 | 8 | Critical | No |
| 4 | 1Password | AST-13 | 3 | 2 | 2 | 7 | High | No |
| 5 | AI model provider | AST-06 | 3 | 2 | 1 | 6 | High | No |
| 6 | Device management (MDM) | AST-08 | 1 | 2 | 3 | 6 | High | No |
| 7 | Stripe | AST-14 | 2 | 3 | 1 | 6 | High | No |
| 8 | HubSpot | AST-15 | 2 | 2 | 1 | 5 | Medium | No |
| 9 | Notion | AST-12 | 2 | 2 | 1 | 5 | Medium | Yes (80%) |
| 10 | Slack | AST-11 | 2 | 2 | 1 | 5 | Medium | No |
| 11 | Linear | AST-16 | 1 | 1 | 1 | 3 | Low | No |
| 12 | Zoom | AST-17 | 1 | 1 | 1 | 3 | Low | No |

| Tier | Vendors | Assessed |
|---|---|---|
| Critical | 3 | 0 |
| High | 4 | 0 |
| Medium | 3 | 1 |
| Low | 2 | 0 |

**Gap:** only 1 of 12 vendors has been assessed, and it is a Medium tier vendor. The three Critical vendors (AWS, GitHub and Google Workspace) are not yet assessed, so they go first.

## Overall vendor risk matrix

| Criticality \ Security band | Strong (90% or more) | Acceptable (75 to 89%) | Weak (60 to 74%) | Unacceptable (below 60%) |
|---|---|---|---|---|
| Critical | Medium | High | Critical | Critical |
| High | Low | Medium | High | Critical |
| Medium | Low | Medium | High | High |
| Low | Low | Low | Medium | Medium |

## Result for Notion

| Measure | Value |
|---|---|
| Criticality | Medium (score 5) |
| Security score | 40 of 50 (80%), Acceptable (75 to 89%) |
| **Overall vendor risk** | **Medium** |
| Decision | **Approve with conditions** (see the [report](vendor-assessment-report.md)) |
| Next review | November 2027, or when the SOC 2 report renews |

## Assessment queue

| Order | Vendor | Tier | Target |
|---|---|---|---|
| 1 | AWS | Critical | Q1 2027 |
| 2 | GitHub | Critical | Q1 2027 |
| 3 | Google Workspace | Critical | Q1 2027 |
| 4 | 1Password | High | Q1 2027 |
| 5 | AI model provider | High | Q1 2027 |
| 6 | Device management (MDM) | High | Q1 2027 |
| 7 | Stripe | High | Q1 2027 |
| 8 | HubSpot | Medium | Q2 2027 |
| 9 | Slack | Medium | Q2 2027 |
| 10 | Linear | Low | At renewal |
| 11 | Zoom | Low | At renewal |

This queue is tracked as action ACT-04 in the [dashboard](../06-compliance-dashboard/README.md).

---

*NovaCloud AI Solutions is a fictional company. All people, systems, incidents, ratings and dates are examples created for skills practice and portfolio use. This is not legal advice or a compliance determination. Framework references are paraphrased pointers, so verify them against the source text before relying on them.*

Author: Augustine Ozor, AI Governance and Cybersecurity GRC. [GitHub](https://github.com/AugustineOzor) · [LinkedIn](https://www.linkedin.com/in/augustinetettehozor)
