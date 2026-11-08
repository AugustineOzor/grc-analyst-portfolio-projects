# Third-party vendor security questionnaire (template)

[← Project 3 README](README.md)

Use this questionnaire to assess a supplier that will handle NovaCloud AI Solutions data or provide a service the company depends on. It has **25 questions in five sections**, with five questions in each.

## How to use it

1. **Tier the vendor first** with the criticality scorecard below, so the depth of review matches the risk.
2. **Send the questionnaire** to the vendor, or complete it yourself from their published security documents (trust center, security page, data processing addendum, audit report summaries).
3. **Score each answer:** Yes = 2, Partial = 1, No = 0. If a vendor gives no evidence, score 0 and note "not evidenced".
4. **Calculate the percentage** (total ÷ 50) and read the security band.
5. **Combine** the band with the criticality tier in the risk matrix to get the overall vendor risk, then decide.

| Score | Meaning |
|---|---|
| Yes = 2 | The control is in place and evidenced for the plan or service you will use |
| Partial = 1 | In place in part, only on a higher plan, or evidence is incomplete |
| No = 0 | Not in place, or no evidence |

## Step 1: criticality scorecard

Score each factor from 1 to 3 and add them up (3 to 9).

| Factor | 1 | 2 | 3 |
|---|---|---|---|
| Data sensitivity | No company or customer data | Internal or business contact data | Customer documents, personal data, secrets or source code |
| Business dependency | Easily replaced; little impact if down | Important but workable for a few days without it | Core service; outage stops the business |
| Access level | No access to our systems | Limited access through a user account | Administrative or infrastructure access |

| Total | Criticality tier |
|---|---|
| 8 to 9 | Critical |
| 6 to 7 | High |
| 4 to 5 | Medium |
| 3 | Low |

## Step 2: questionnaire

### Governance

| # | Question | Why it matters | Evidence to request | Response (Yes / Partial / No) | Score (2 / 1 / 0) |
|---|---|---|---|---|---|
| G1 | Is there a documented information security policy that staff must acknowledge, with a regular review? | Shows management direction and accountability. | Policy with approval date; Trust Center page |  |  |
| G2 | Does the vendor hold an independent ISMS certification or an annual SOC 2 Type II report? | Independent assurance that controls operate over time. | SOC 2 Type II report or ISO 27001 certificate, with scope and dates |  |  |
| G3 | Do all staff receive security awareness training at least once a year? | People are the most common route to a breach. | Training policy; completion rates |  |  |
| G4 | Are employees screened before hire? | Reduces insider risk. | Screening policy statement |  |  |
| G5 | Does the vendor assess and contract with its own subprocessors? | Your data is only as safe as the weakest link in the chain. | Subprocessor list; vendor management policy |  |  |

### Access Control

| # | Question | Why it matters | Evidence to request | Response (Yes / Partial / No) | Score (2 / 1 / 0) |
|---|---|---|---|---|---|
| A1 | Can customer users turn on multi-factor authentication? | Blocks most credential theft. | Product documentation on MFA options |  |  |
| A2 | Are single sign-on and automated provisioning available to NovaCloud's plan? | Central control of joiners and leavers. | Plan comparison; SSO and provisioning documentation |  |  |
| A3 | Does the vendor limit its own staff's access to customer data to what they need? | Limits insider and compromise impact. | Access control policy; description of access reviews |  |  |
| A4 | Is MFA required for the vendor's own staff and admin access? | Protects the vendor's own production systems. | Statement or audit report section on staff MFA |  |  |
| A5 | Can customers see audit logs of access and activity? | Lets you investigate misuse. | Documentation of audit logs and export options |  |  |

### Data Protection

| # | Question | Why it matters | Evidence to request | Response (Yes / Partial / No) | Score (2 / 1 / 0) |
|---|---|---|---|---|---|
| D1 | Is data encrypted in transit with a current protocol? | Protects data on the network. | Security page or configuration statement (TLS version) |  |  |
| D2 | Is customer data encrypted at rest, including backups? | Protects data if storage is accessed. | Security page; audit report section on encryption |  |  |
| D3 | Can customers manage their own encryption keys? | Gives control and a way to cut off access. | Key management documentation |  |  |
| D4 | Are customers' data and the vendor's environments separated? | Prevents one tenant or a test system exposing another. | Architecture or security white paper |  |  |
| D5 | Are retention, deletion, return of data and data location documented? | Needed for exit and for privacy duties. | Retention policy; DPA deletion and return terms; region options |  |  |

### Incident Response

| # | Question | Why it matters | Evidence to request | Response (Yes / Partial / No) | Score (2 / 1 / 0) |
|---|---|---|---|---|---|
| I1 | Does the vendor have a documented incident response process? | Shows it can detect and respond. | Incident response policy summary; monitoring description |  |  |
| I2 | Does the vendor commit to a time limit for telling customers about a breach? | Lets you meet your own deadlines. | DPA clause with a number of hours or days |  |  |
| I3 | Are critical systems logged and monitored? | Detection depends on logs. | Logging and monitoring description; audit report |  |  |
| I4 | Are redundancy, backups and recovery targets documented? | Availability and recovery. | Continuity and recovery summary; RTO and RPO; backup description |  |  |
| I5 | Are external penetration tests run each year, with a way for researchers to report issues? | Finds weaknesses before attackers do. | Penetration test summary; disclosure or bug bounty policy |  |  |

### Compliance

| # | Question | Why it matters | Evidence to request | Response (Yes / Partial / No) | Score (2 / 1 / 0) |
|---|---|---|---|---|---|
| C1 | Is there an annual SOC 2 Type II report? | Evidence of operating controls. | SOC 2 Type II report (under NDA) and its audit period |  |  |
| C2 | Is the vendor certified to ISO 27001 or related standards? | Evidence of a managed security program. | ISO certificates with scope and expiry dates |  |  |
| C3 | Does the vendor act as a processor under a data processing addendum covering GDPR and CCPA? | Needed for personal data in your documents. | Signed or incorporated DPA; subprocessor list |  |  |
| C4 | Will the vendor sign sector agreements such as a HIPAA BAA if needed? | Matters if regulated data is ever stored. | BAA or sector terms, and the plan they need |  |  |
| C5 | Will the vendor share audit reports and certificates with customers? | Lets you verify claims. | Trust center, or the process to request reports |  |  |

## Step 3: security score and overall risk

| Section | Score | Maximum |
|---|---|---|
| Governance | | 10 |
| Access Control | | 10 |
| Data Protection | | 10 |
| Incident Response | | 10 |
| Compliance | | 10 |
| **Total** | | **50** |

| Security band | Percentage |
|---|---|
| Strong | 90% or more |
| Acceptable | 75 to 89% |
| Weak | 60 to 74% |
| Unacceptable | Below 60% |

**Overall vendor risk matrix**

| Criticality \ Security band | Strong | Acceptable | Weak | Unacceptable |
|---|---|---|---|---|
| Critical | Medium | High | Critical | Critical |
| High | Low | Medium | High | Critical |
| Medium | Low | Medium | High | High |
| Low | Low | Low | Medium | Medium |

**Decision options:** approve, approve with conditions (record the conditions and a review date), or reject.

---

*NovaCloud AI Solutions is a fictional company. All people, systems, incidents, ratings and dates are examples created for skills practice and portfolio use. This is not legal advice or a compliance determination. Framework references are paraphrased pointers, so verify them against the source text before relying on them.*

Author: Augustine Ozor, AI Governance and Cybersecurity GRC. [GitHub](https://github.com/AugustineOzor) · [LinkedIn](https://www.linkedin.com/in/augustinetettehozor)
