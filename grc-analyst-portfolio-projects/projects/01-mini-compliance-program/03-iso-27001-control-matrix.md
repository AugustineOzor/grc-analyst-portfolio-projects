# ISO 27001:2022 control matrix

[← Project 1 README](README.md)

The matrix assesses 23 Annex A controls from all four themes for NovaCloud AI Solutions. The full Annex A has 93 controls; these 23 were chosen because they matter most for a small cloud startup and cover each theme. A complete Statement of Applicability would address all 93, with a justification for any that are excluded.

## How to read it

| Status | Meaning |
|---|---|
| 🟩 Implemented | The control operates and is owned. Improvements may still be listed. |
| 🟨 Partial | Some of the control operates, but it is incomplete or not formally approved. |
| 🟥 Planned | No control operates yet. This is a gap with a planned action. |

| Maturity | Description |
|---|---|
| 1 Initial | Done ad hoc, or not done |
| 2 Developing | Partly in place, informal or not documented |
| 3 Defined | Documented, owned and applied consistently |
| 4 Managed | Measured and reviewed regularly |
| 5 Optimized | Continuously improved from measurements |

## Summary

| Annex A theme | Controls assessed | Implemented | Partial | Planned | Average maturity |
|---|---|---|---|---|---|
| Organizational | 11 | 2 | 6 | 3 | 1.9 |
| People | 2 | 0 | 1 | 1 | 1.5 |
| Physical | 1 | 0 | 1 | 0 | 2.0 |
| Technological | 9 | 5 | 4 | 0 | 2.6 |
| **Total** | **23** | **7** | **12** | **4** | **2.1** |

**Reading the result:** 7 of 23 controls (30%) are implemented and 4 are not started. Technological controls are strongest (average maturity 2.6) because the team is engineering-led. People and organizational controls are weakest, which is typical for a young company: the technology works, but the policies, training and oversight around it are not yet written down.

## Control matrix

| Control ID | Control | Requirement | Current Status | Maturity | Owner | Action Needed |
|---|---|---|---|---|---|---|
| A.5.1 | Policies for information security | Define, approve, publish and review information security policies. | 🟨 Partial | 2 / 5 | CEO | Approve and publish the policy set; set an annual review date. |
| A.5.2 | Information security roles and responsibilities | Define and allocate security roles and responsibilities. | 🟨 Partial | 2 / 5 | CEO | Appoint a security lead in writing and publish a RACI. |
| A.5.9 | Inventory of information and other associated assets | Keep an inventory of information and associated assets, with owners. | 🟩 Implemented | 3 / 5 | Operations Manager | Review quarterly and add data owners. |
| A.5.10 | Acceptable use of information and other associated assets | Define and apply rules for acceptable use of information and assets. | 🟥 Planned | 1 / 5 | GRC Analyst | Write the policy and collect signed acknowledgments. |
| A.5.15 | Access control | Control access to information and assets based on business and security needs. | 🟩 Implemented | 3 / 5 | CTO | Add a quarterly access review. |
| A.5.19 | Information security in supplier relationships | Manage information security risks in supplier relationships. | 🟨 Partial | 2 / 5 | Operations Manager | Assess the remaining 11 vendors, Critical tier first; add security clauses to contracts. |
| A.5.23 | Information security for use of cloud services | Manage security across the life of cloud service use. | 🟨 Partial | 2 / 5 | CTO | Document shared responsibility and enable an AWS Config conformance pack. |
| A.5.24 | Information security incident management planning and preparation | Plan and prepare for security incident management. | 🟨 Partial | 2 / 5 | CTO | Close the five tabletop actions; schedule an annual exercise. |
| A.5.30 | ICT readiness for business continuity | Plan ICT readiness to support business continuity. | 🟥 Planned | 1 / 5 | CTO | Define RTO and RPO and test failover. |
| A.5.34 | Privacy and protection of PII | Protect privacy and personal data as required by law and contract. | 🟨 Partial | 2 / 5 | CEO | Create a record of processing and a DPA template; write a data subject request procedure. |
| A.5.36 | Compliance with policies, rules and standards for information security | Check regularly that policies, rules and standards are followed. | 🟥 Planned | 1 / 5 | GRC Analyst | Run the first internal audit (Project 7) and schedule an annual program. |
| A.6.3 | Information security awareness, education and training | Give staff security awareness, education and training. | 🟥 Planned | 1 / 5 | GRC Analyst | Run onboarding and annual training, plus phishing simulations. |
| A.6.7 | Remote working | Protect information when people work remotely. | 🟨 Partial | 2 / 5 | Operations Manager | Publish a remote working guide covering Wi-Fi, devices and shared spaces. |
| A.7.7 | Clear desk and clear screen | Apply clear desk and clear screen rules. | 🟨 Partial | 2 / 5 | Operations Manager | Add clear desk and screen guidance to the acceptable use policy. |
| A.8.1 | User endpoint devices | Protect information on user endpoint devices. | 🟩 Implemented | 3 / 5 | Operations Manager | Report MDM compliance monthly. |
| A.8.2 | Privileged access rights | Restrict and manage privileged access rights. | 🟨 Partial | 2 / 5 | CTO | Remove standing admin; use time-limited SSO roles. |
| A.8.5 | Secure authentication | Use secure authentication for access to systems. | 🟩 Implemented | 3 / 5 | CTO | Move to phishing-resistant MFA (see tabletop action ACT-08). |
| A.8.7 | Protection against malware | Protect against malware. | 🟩 Implemented | 3 / 5 | Operations Manager | Review alerts weekly. |
| A.8.8 | Management of technical vulnerabilities | Find and fix technical vulnerabilities in time. | 🟨 Partial | 2 / 5 | Engineering Lead | Scan weekly and set fix times by severity. |
| A.8.13 | Information backup | Keep backup copies and test them. | 🟨 Partial | 2 / 5 | CTO | Run and document a restore test each quarter. |
| A.8.15 | Logging | Produce, protect and review logs of activity. | 🟨 Partial | 2 / 5 | CTO | Extend retention to 12 months and add alerts for high-risk events. |
| A.8.24 | Use of cryptography | Define and apply rules for the use of cryptography. | 🟩 Implemented | 3 / 5 | CTO | Document key management and rotation. |
| A.8.32 | Change management | Control changes to systems and processes. | 🟩 Implemented | 3 / 5 | Engineering Lead | Add a second reviewer for infrastructure changes. |

Each action is tracked with an owner and due date in the [remediation action list](../06-compliance-dashboard/README.md) and the dashboard workbook.

---

*NovaCloud AI Solutions is a fictional company. All people, systems, incidents, ratings and dates are examples created for skills practice and portfolio use. This is not legal advice or a compliance determination. Framework references are paraphrased pointers, so verify them against the source text before relying on them.*

Author: Augustine Ozor, AI Governance and Cybersecurity GRC. [GitHub](https://github.com/AugustineOzor) · [LinkedIn](https://www.linkedin.com/in/augustinetettehozor)
