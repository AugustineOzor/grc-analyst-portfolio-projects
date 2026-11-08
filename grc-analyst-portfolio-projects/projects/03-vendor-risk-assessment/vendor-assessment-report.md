# Vendor assessment report: Notion

[← Project 3 README](README.md)

**Prepared by:** GRC Analyst · **Date:** 19 November 2026 · **For:** Operations Manager and CTO

## Summary

Notion is NovaCloud AI Solutions's internal wiki. It scores **40 of 50 (80%)** against the 25-question template, which is an *Acceptable* security band. Notion is a **Medium** criticality vendor, so the overall vendor risk is **Medium**. We recommend approving it **with conditions**.

| Section | Score | Maximum | Percentage |
|---|---|---|---|
| Governance | 8 | 10 | 80% |
| Access Control | 8 | 10 | 80% |
| Data Protection | 8 | 10 | 80% |
| Incident Response | 7 | 10 | 70% |
| Compliance | 9 | 10 | 90% |
| **Total** | **40** | **50** | **80%** |

## What is strong

- Independent assurance: annual SOC 2 Type II audit and ISO 27001, 27017, 27018 and 27701 certifications.
- Encryption in transit (TLS 1.2 or higher) and at rest (AES-256), including backups.
- Annual external penetration tests and a public bug bounty program.
- MFA is available to all users and required for Notion's own staff.

## What is weaker

- Single sign-on, provisioning, audit logs and customer-managed keys are limited to the Enterprise plan.
- The breach notification time and data location choices were not confirmed in public pages.
- Incident response and recovery targets are not published in detail.

## Conditions of approval

| # | Condition | Owner | Due |
|---|---|---|---|
| 1 | Do not store customer files, personal data, passwords or API keys in Notion; add this to the acceptable use policy | GRC Analyst | 15 Jan 2027 |
| 2 | Turn on two-step verification for every user, and restrict public sharing and guest access | Operations Manager | 15 Dec 2026 |
| 3 | Confirm the breach notification time in the data processing addendum, and request the SOC 2 report under NDA | Operations Manager | 31 Jan 2027 |
| 4 | Decide whether to enable Notion AI; if enabled, apply condition 1 to it | CTO | 31 Jan 2027 |
| 5 | Review again in November 2027 or when the SOC 2 report renews | GRC Analyst | 30 Nov 2027 |

## Recommendation

Approve Notion for internal documentation only, subject to the conditions above. Record it in the vendor register as Medium tier, owner Operations Manager. Move on to assessing the Critical vendors next.

---

*NovaCloud AI Solutions is a fictional company. All people, systems, incidents, ratings and dates are examples created for skills practice and portfolio use. This is not legal advice or a compliance determination. Framework references are paraphrased pointers, so verify them against the source text before relying on them.*

Author: Augustine Ozor, AI Governance and Cybersecurity GRC. [GitHub](https://github.com/AugustineOzor) · [LinkedIn](https://www.linkedin.com/in/augustinetettehozor)
