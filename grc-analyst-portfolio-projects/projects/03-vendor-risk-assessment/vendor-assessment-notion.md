# Completed vendor assessment: Notion

[← Project 3 README](README.md)

| Item | Detail |
|---|---|
| Vendor and service | Notion Labs, Inc.: Notion workspace (internal wiki and documentation), including its AI features |
| Used by NovaCloud for | Policies, runbooks and internal documentation ([AST-12](../01-mini-compliance-program/02-asset-inventory.md)) |
| Assessment date | 19 November 2026 |
| Method | Desk review of Notion's **published** security documentation, using the [template](vendor-questionnaire-template.md). The vendor was not contacted and no audit report was reviewed. |
| Result | **40 of 50 (80%): Acceptable.** 15 Yes, 10 Partial, 0 No. |

## Score by section

| Section | Score | Maximum | Percentage |
|---|---|---|---|
| Governance | 8 | 10 | 80% |
| Access Control | 8 | 10 | 80% |
| Data Protection | 8 | 10 | 80% |
| Incident Response | 7 | 10 | 70% |
| Compliance | 9 | 10 | 90% |
| **Total** | **40** | **50** | **80%** |

## Question-level results

### Governance (8 of 10)

| # | Question | Response (score) | Evidence from public documentation | Source |
|---|---|---|---|---|
| G1 | Is there a documented information security policy that staff must acknowledge, with a regular review? | **Partial** (1) | Policies are held in the Trust Center and staff must read and acknowledge the security policy, and internal security audits run at least yearly. The review cadence of the policy itself is not stated. | Security practices page; Trust Center |
| G2 | Does the vendor hold an independent ISMS certification or an annual SOC 2 Type II report? | **Yes** (2) | Annual SOC 2 Type II audit and ISO 27001 certification, plus ISO 27017, 27018 and 27701. | Trust Center; Notion security page |
| G3 | Do all staff receive security awareness training at least once a year? | **Partial** (1) | Developer training is stated to happen at least yearly and staff acknowledge the security policy. Company-wide annual training is not stated explicitly. | Security practices page |
| G4 | Are employees screened before hire? | **Yes** (2) | Background checks are performed on employees at hire, in line with local law. | Security practices page |
| G5 | Does the vendor assess and contract with its own subprocessors? | **Yes** (2) | Subprocessors are reviewed for privacy, security and confidentiality before engagement and bound by a written agreement; a subprocessor list is published. | Notion AI security page; Trust Center |

### Access Control (8 of 10)

| # | Question | Response (score) | Evidence from public documentation | Source |
|---|---|---|---|---|
| A1 | Can customer users turn on multi-factor authentication? | **Yes** (2) | Two-step verification is available on all plan types. | Security practices page |
| A2 | Are single sign-on and automated provisioning available to NovaCloud's plan? | **Partial** (1) | SAML single sign-on and SCIM provisioning are offered, but on the Enterprise plan. A smaller plan would not have them. | Notion security page |
| A3 | Does the vendor limit its own staff's access to customer data to what they need? | **Yes** (2) | Least privilege access is listed among its protections. | Notion security page |
| A4 | Is MFA required for the vendor's own staff and admin access? | **Yes** (2) | MFA is required for all employees to sign in to the identity provider, and for every system that supports it. | Security practices page |
| A5 | Can customers see audit logs of access and activity? | **Partial** (1) | Workspace owners can see detailed security-related activity, with integration to a SIEM or DLP tool. Plan limits may apply. | Security practices page; Notion security page |

### Data Protection (8 of 10)

| # | Question | Response (score) | Evidence from public documentation | Source |
|---|---|---|---|---|
| D1 | Is data encrypted in transit with a current protocol? | **Yes** (2) | TLS 1.2 or higher is used for data in transit. | Security practices page; Trust Center |
| D2 | Is customer data encrypted at rest, including backups? | **Yes** (2) | All customer data on internal networks, cloud storage, databases and backups is encrypted at rest with AES-256. | Trust Center |
| D3 | Can customers manage their own encryption keys? | **Partial** (1) | Enterprise customers can manage keys through AWS KMS. This is not available on smaller plans. | Trust Center |
| D4 | Are customers' data and the vendor's environments separated? | **Yes** (2) | Customer accounts are logically separated in production, and development, test and production are separate environments. | Security practices page |
| D5 | Are retention, deletion, return of data and data location documented? | **Partial** (1) | Some deletion terms are published (for example AI embeddings are deleted within 60 days of a page or workspace being deleted). Data location choices were not confirmed in the pages reviewed. | Notion AI security page |

### Incident Response (7 of 10)

| # | Question | Response (score) | Evidence from public documentation | Source |
|---|---|---|---|---|
| I1 | Does the vendor have a documented incident response process? | **Partial** (1) | A SIEM sends event notifications to security staff in real time. A full incident response plan is not published. | Security practices page |
| I2 | Does the vendor commit to a time limit for telling customers about a breach? | **Partial** (1) | Public pages say customers are covered by the data processing addendum, but a specific notification time was not confirmed in the sources reviewed. Check the addendum. | Data Processing Addendum (to confirm) |
| I3 | Are critical systems logged and monitored? | **Yes** (2) | Logging is enabled on all critical systems and a SIEM is used for incident and event management. | Security practices page |
| I4 | Are redundancy, backups and recovery targets documented? | **Partial** (1) | Hosting is described as fully redundant on AWS and backups are encrypted. Recovery time and recovery point targets are not published. | Security practices page; Trust Center |
| I5 | Are external penetration tests run each year, with a way for researchers to report issues? | **Yes** (2) | Annual third-party penetration tests of the web, mobile and desktop apps, and a public bug bounty program. | Notion security page; Trust Center |

### Compliance (9 of 10)

| # | Question | Response (score) | Evidence from public documentation | Source |
|---|---|---|---|---|
| C1 | Is there an annual SOC 2 Type II report? | **Yes** (2) | Annual SOC 2 Type II audit; the report is available under NDA through the Trust Center. | Trust Center; Notion MSA FAQ |
| C2 | Is the vendor certified to ISO 27001 or related standards? | **Yes** (2) | ISO 27001, 27017, 27018 and 27701 certifications are listed. | Notion security page |
| C3 | Does the vendor act as a processor under a data processing addendum covering GDPR and CCPA? | **Yes** (2) | A data processing addendum applies, the vendor acts as processor for uploaded personal data, and controls are aligned to GDPR and CCPA. | Notion security page; Data Processing Addendum |
| C4 | Will the vendor sign sector agreements such as a HIPAA BAA if needed? | **Partial** (1) | A business associate agreement is available, but to Enterprise customers. NovaCloud does not need it today. | Notion security page |
| C5 | Will the vendor share audit reports and certificates with customers? | **Yes** (2) | The Trust Center lists audit reports, certifications and penetration test results; some are available under NDA. | Trust Center; Notion MSA FAQ |


## Limits of this assessment

- It relies on public pages that the vendor can change. Page contents were read on 19 November 2026.
- Several features (single sign-on, audit logs, customer-managed keys, the HIPAA agreement) are offered on the Enterprise plan. Answers are scored for the plan NovaCloud would actually use, so those are marked Partial.
- The breach notification time (I2) and data location choices (D5) were not confirmed in the sources reviewed. They should be checked in the data processing addendum and by asking the vendor.
- The SOC 2 Type II report is available under NDA and was not reviewed. Reading it is the main follow-up.

## Sources

- **Security practices page:** <https://www.notion.com/help/security-and-privacy>
- **Notion security page:** <https://www.notion.com/security>
- **Trust Center:** <https://trust.notion.com/controls>
- **Notion AI security page:** <https://www.notion.com/help/notion-ai-security-practices>
- **Notion MSA FAQ:** <https://notion.notion.site/MSA-FAQ-38eefdeead0580199728e2ae73e02ba4>
- **Data Processing Addendum:** <https://notion.notion.site/Data-Processing-Addendum-361b540101274b1fa7e16b90402b0d99>

---

*NovaCloud AI Solutions is a fictional company. All people, systems, incidents, ratings and dates are examples created for skills practice and portfolio use. This is not legal advice or a compliance determination. Framework references are paraphrased pointers, so verify them against the source text before relying on them.*

Author: Augustine Ozor, AI Governance and Cybersecurity GRC. [GitHub](https://github.com/AugustineOzor) · [LinkedIn](https://www.linkedin.com/in/augustinetettehozor)
