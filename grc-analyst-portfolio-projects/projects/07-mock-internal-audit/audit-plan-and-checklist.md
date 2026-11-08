# Internal audit plan and checklist

[← Project 7 README](README.md)

## Audit plan

| Item | Detail |
|---|---|
| Audit | First internal audit of the mini ISMS (ISO/IEC 27001:2022 clause 9.2) |
| Objective | Check whether the work in Projects 1 to 6 meets the stated requirements, and whether the claims in the documents are supported by evidence |
| Scope | The scope, assets, control matrix, risk register, vendor process, incident response plan, SOC 2 mapping and dashboard of NovaCloud AI Solutions |
| Criteria | ISO/IEC 27001:2022 clauses 4 to 10 and the Annex A controls sampled; the company's own plans and targets |
| Method | Document review, reconciliation across documents, and sampling of controls. Guided by the audit principles in ISO 19011 |
| Sample | 10 of the 23 controls, chosen to cover all four themes and the highest risks: A.5.1, A.5.9, A.5.15, A.5.19, A.5.24, A.6.3, A.8.5, A.8.13, A.8.15, A.8.24 |
| Fieldwork | 08 Dec 2026 to 10 Dec 2026 (as at 10 Dec 2026) |
| Report issued | 11 Dec 2026 |
| Auditor | GRC Analyst |

**Independence limit:** the auditor also wrote the documents being audited. A real internal audit needs an auditor who is independent of the work. In this portfolio exercise that limit is accepted and stated.

## Rating scale

| Finding type | Meaning |
|---|---|
| Nonconformity (major) | A requirement is not met, or a failure that undermines the system's ability to achieve its intended results |
| Nonconformity (minor) | A requirement is partly met, or a single lapse that does not undermine the system |
| Observation | Not a nonconformity, but a weakness or an opportunity to improve |

| Severity | Meaning |
|---|---|
| High | Must be fixed before an external audit |
| Medium | Fix within the next quarter |
| Low | Fix when convenient, track it |

## Cross-checks across the portfolio

| Check | Result | Outcome |
|---|---|---|
| Control status counts agree across the matrix, dashboard image and workbook | 7 implemented, 12 partial, 4 planned in all three | Pass |
| Every control cited in the risk register exists in the control matrix | All 12 risks checked | Pass |
| Every control cited in the action list exists in the matrix | All 24 actions checked | Pass |
| All five tabletop gaps have a matching action | ACT-06 to ACT-10 present | Pass |
| Vendor count agrees between the scorecard and the control matrix | 12 vendors; 1 assessed in both | Pass |
| Open actions past due on 10 Dec 2026 | ACT-02, ACT-06 (2 overdue) | Finding |
| Risk mitigations link to action IDs | Mitigations are free text with no action IDs | Finding |

## Internal audit checklist

| Control | Evidence reviewed | Finding | Severity | Action plan |
|---|---|---|---|---|
| A.5.1 Policies for information security | Control matrix; draft policy set | F-01: no approved policy (major nonconformity) | High | ACT-01 |
| A.5.9 Inventory of assets | Asset inventory of 17 assets | Conforms. F-02: no data inventory (observation) | Low | ACT-25 |
| A.5.15 Access control | Control matrix; mapping CC6.1 to CC6.3 | F-03: no technical evidence on file (minor) | Medium | ACT-18 |
| A.5.19 Supplier relationships | Vendor template; Notion assessment; scorecard | F-04: 1 of 12 vendors assessed (minor) | Medium | ACT-04 |
| A.5.24 Incident management | Incident response plan; tabletop; report | F-05: tabletop action ACT-06 overdue (minor) | Medium | ACT-06 |
| A.6.3 Awareness and training | Control matrix; tabletop report | F-06: no training or records (minor) | Medium | ACT-14 |
| A.8.5 Secure authentication | Control matrix; tabletop report | F-03 and F-09: no evidence; MFA can be phished (observation) | Medium | ACT-18, ACT-08 |
| A.8.13 Information backup | Control matrix; risk R-07 | F-07: restore never tested (minor) | Medium | ACT-11 |
| A.8.15 Logging | Control matrix; tabletop report | F-08: 90-day retention and no alerts (observation) | Medium | ACT-09 |
| A.8.24 Use of cryptography | Control matrix; mapping CC6.7 and C1.1 | Design conforms. F-03: evidence not on file | Medium | ACT-18 |

Details of each finding are in the [audit report](audit-report.md).

---

*NovaCloud AI Solutions is a fictional company. All people, systems, incidents, ratings and dates are examples created for skills practice and portfolio use. This is not legal advice or a compliance determination. Framework references are paraphrased pointers, so verify them against the source text before relying on them.*

Author: Augustine Ozor, AI Governance and Cybersecurity GRC. [GitHub](https://github.com/AugustineOzor) · [LinkedIn](https://www.linkedin.com/in/augustinetettehozor)
