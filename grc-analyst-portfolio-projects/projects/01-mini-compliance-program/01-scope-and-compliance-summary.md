# Scope and compliance goal (one-page summary)

[← Project 1 README](README.md)

**Company:** NovaCloud AI Solutions, a 10-person, fully remote startup that sells an AI document analysis service built on AWS.
**Prepared by:** GRC Analyst · **Baseline date:** 2 November 2026

## Compliance goal

Reach readiness for an **ISO/IEC 27001:2022 Stage 1 audit by Q3 2027**. Customers in the US and EU increasingly ask for certification in security questionnaires, and the work also prepares the ground for a SOC 2 report later.

## Scope of the ISMS

| In scope | Out of scope |
|---|---|
| The NovaCloud platform on AWS (application, database, storage, backups, logs) | Customers' own environments and devices |
| All ten staff, their laptops and the SaaS tools used for work (17 assets, see the [inventory](02-asset-inventory.md)) | Third-party model providers' internal systems (managed through supplier controls) |
| Remote working from home offices | Physical data centers (covered by AWS under the shared responsibility model) |

## Approach

1. Listed the assets and agreed the scope.
2. Assessed 23 Annex A 2022 controls from all four themes against what is actually in place.
3. Recorded status, a maturity score from 1 to 5, an owner and the action needed for each.
4. Turned every gap into a tracked action with a due date.

## Result

| 23 controls assessed | Implemented | Partial | Planned | Average maturity |
|---|---|---|---|---|
| | 7 (30%) | 12 (52%) | 4 (17%) | 2.1 of 5 |

**Strengths:** MFA on the main systems, managed and encrypted laptops, encryption in transit and at rest, and pull-request reviews for code changes.

**Main gaps:** no approved policy set, no acceptable use policy, no staff training, no tested backup restore, and only one of twelve vendors assessed.

## Priorities for the next 90 days

1. Approve and publish the policy set, and appoint the security lead (A.5.1, A.5.2).
2. Close the incident response gaps found in the tabletop (A.5.24).
3. Prove backups work with a restore test (A.8.13) and define recovery targets (A.5.30).
4. Start staff awareness training (A.6.3) and assess the Critical-tier vendors (A.5.19).

Full detail: [control matrix](03-iso-27001-control-matrix.md).

---

*NovaCloud AI Solutions is a fictional company. All people, systems, incidents, ratings and dates are examples created for skills practice and portfolio use. This is not legal advice or a compliance determination. Framework references are paraphrased pointers, so verify them against the source text before relying on them.*

Author: Augustine Ozor, AI Governance and Cybersecurity GRC. [GitHub](https://github.com/AugustineOzor) · [LinkedIn](https://www.linkedin.com/in/augustinetettehozor)
