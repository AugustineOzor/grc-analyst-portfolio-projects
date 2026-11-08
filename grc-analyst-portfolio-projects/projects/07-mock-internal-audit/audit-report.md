# Internal audit report

[← Project 7 README](README.md)

| Item | Detail |
|---|---|
| Organization | NovaCloud AI Solutions |
| Audit | Internal audit of the mini ISMS, Projects 1 to 6 |
| Criteria | ISO/IEC 27001:2022 and the company's own plans |
| Fieldwork | 08 Dec 2026 to 10 Dec 2026 |
| Report date | 11 Dec 2026 |
| Auditor | GRC Analyst (not independent of the work; see the [plan](audit-plan-and-checklist.md)) |

## 1. Conclusion

The ISMS is **not yet ready for an external Stage 1 audit**, but it is on a credible path. The design work is good: scope, assets, risks, an incident plan and a vendor method all exist and agree with each other. The gaps are in **approval, evidence and follow-through**. One major nonconformity (no approved policy) must be closed first. Seven of the 23 controls (30%) are implemented, and none of the "Implemented" claims has technical evidence on file yet.

## 2. Results

| Controls sampled | Nonconformities (major) | Nonconformities (minor) | Observations | High | Medium | Low |
|---|---|---|---|---|---|---|
| 10 of 23 | 1 | 5 | 4 | 1 | 7 | 2 |

Of the 10 controls sampled, none was found fully effective and evidenced. The cryptography and asset inventory controls are well designed, but evidence is missing or incomplete.

## 3. Findings

| ID | Control | Type | Severity | Finding | Evidence |
|---|---|---|---|---|---|
| F-01 | A.5.1 | Nonconformity (major) | High | No approved information security policy exists. Ten policies are in draft and none has been approved by top management (ISO 27001 clause 5.2 and A.5.1). | Control matrix row A.5.1 (Partial, maturity 2); no approval record |
| F-02 | A.5.9 | Observation | Low | The asset inventory lists 17 systems with owners and classification, but not the information they hold (customer documents, personal data, logs). | Asset inventory (Project 1) |
| F-03 | A.5.15, A.8.5, A.8.24 | Nonconformity (minor) | Medium | Three controls are rated Implemented, but no technical evidence is on file. The SOC 2 evidence has not been captured (0 of 26 items). | Control matrix; evidence guide status |
| F-04 | A.5.19 | Nonconformity (minor) | Medium | The vendor process exists, but only 1 of 12 vendors is assessed, and it is a Medium tier vendor. The 3 Critical vendors (AWS, GitHub, Google Workspace) have not been assessed. | Vendor risk scorecard |
| F-05 | A.5.24 | Nonconformity (minor) | Medium | Corrective actions from the 18 November tabletop are not all on time. ACT-06 (after-hours on-call rota) was due on 5 December and is still open. | Tabletop report; action list on 10 Dec 2026 |
| F-06 | A.6.3 | Nonconformity (minor) | Medium | There is no awareness training and no training records. The control is Planned, yet the tabletop showed a staff member entering credentials on a fake page. | Control matrix; tabletop report |
| F-07 | A.8.13 | Nonconformity (minor) | Medium | Backups run, but no restore has ever been tested, so recovery is unproven and the recovery targets are undefined. | Control matrix; risk R-07 |
| F-08 | A.8.15 | Observation | Medium | Logs are kept for 90 days and there are no alerts for high-risk events. In the tabletop the attacker was active for about four hours before anyone noticed. | Control matrix; tabletop report |
| F-09 | A.8.5 | Observation | Medium | MFA is enforced, but by authenticator app and push approval. The tabletop showed that session-capturing phishing can bypass this. | Tabletop report |
| F-10 | A.5.2 and programme | Observation | Low | ACT-02 (appoint the security lead in writing) was due on 5 December and has not started. Risk mitigations are not linked to action IDs, so progress cannot be traced from the risk register. | Action list on 10 Dec 2026; risk register |

## 4. Good practice noted

- The documents **agree with each other**: control counts, risk controls, action IDs and vendor counts reconcile across the matrix, register, dashboard and workbook.
- The tabletop **tested a realistic weakness** (phishable MFA) and every gap became an owned, dated action.
- Risks are shown at **inherent, current and target** levels, which makes progress measurable.
- The vendor assessment **states what could not be confirmed**, which is the honest way to use public documents.

## 5. Corrective action plan

| CAR | Finding | Action ID | Corrective action | Owner | Due | Severity |
|---|---|---|---|---|---|---|
| CAR-01 | F-01 | ACT-01 | Approve and publish the policy set; record approval in minutes | CEO | 15 Dec 2026 | High |
| CAR-02 | F-02 | ACT-25 | Add a data inventory with data owners | Operations Manager | 31 Jan 2027 | Low |
| CAR-03 | F-03 | ACT-18 | Capture the evidence items and file them | GRC Analyst | 31 Dec 2026 | Medium |
| CAR-04 | F-04 | ACT-04 | Assess the Critical vendors first, then the rest | Operations Manager | 31 Mar 2027 | Medium |
| CAR-05 | F-05 | ACT-06 | Complete the on-call rota and call tree (re-planned) | CTO | 17 Dec 2026 | Medium |
| CAR-06 | F-06 | ACT-14 | Run onboarding training and the first phishing simulation | GRC Analyst | 31 Jan 2027 | Medium |
| CAR-07 | F-07 | ACT-11 | Define RTO and RPO and run a restore test | CTO | 31 Jan 2027 | Medium |
| CAR-08 | F-08 | ACT-09 | Add alerts and extend log retention to 12 months | CTO | 31 Jan 2027 | Medium |
| CAR-09 | F-09 | ACT-08 | Move admins, then all staff, to security keys | CTO | 28 Feb 2027 | Medium |
| CAR-10 | F-10 | ACT-26 | Appoint the security lead; link every mitigation to an action ID | CEO and GRC Analyst | 18 Dec 2026 | Low |

ACT-25 and ACT-26 are new actions raised by this audit and are added to the [action list](../06-compliance-dashboard/dashboard.md). ACT-06 and ACT-02 were due on 5 December and are re-planned above.

## 6. Lessons learned

1. **"Implemented" needs evidence.** A control is not done until someone can show proof. Capture evidence as the control is set up, not afterwards.
2. **Approval is a control too.** Good documents that nobody has approved do not satisfy the standard.
3. **Link everything to an action ID.** Traceability from risk to action to owner is what lets an audit follow the story.
4. **Test, then trust.** Backups and incident plans only count once they have been exercised.
5. **Check dates.** Two overdue actions in a ten-day window show that tracking needs a regular review, not just a list.

## 7. Next steps

1. Close F-01 (policy approval) before anything else, then re-audit the sampled controls in **January 2027**.
2. Extend the sample to the remaining controls and to the management system clauses (4 to 10) in the next cycle.
3. Plan an annual audit program with an independent auditor, and present these results to the CEO as management review input (clause 9.3).

| Role | Name | Date |
|---|---|---|
| Auditor | GRC Analyst | 11 Dec 2026 |
| Reviewed by | CEO | Pending |

---

*NovaCloud AI Solutions is a fictional company. All people, systems, incidents, ratings and dates are examples created for skills practice and portfolio use. This is not legal advice or a compliance determination. Framework references are paraphrased pointers, so verify them against the source text before relying on them.*

Author: Augustine Ozor, AI Governance and Cybersecurity GRC. [GitHub](https://github.com/AugustineOzor) · [LinkedIn](https://www.linkedin.com/in/augustinetettehozor)
