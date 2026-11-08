# Asset inventory

[← Project 1 README](README.md)

Assets in scope for the ISMS (17 items). Classification follows a simple scale: **Critical** (loss would stop the business or expose customer data), **High**, **Medium**, **Low**.

| ID | Asset | Type | Classification | Owner | Notes |
|---|---|---|---|---|---|
| AST-01 | AWS production account | Cloud account | Critical | CTO | Hosts all production workloads; single account with separate roles per team |
| AST-02 | API and worker services (ECS) | Application | Critical | Engineering Lead | Customer-facing API and document-processing workers |
| AST-03 | PostgreSQL database (RDS) | Database | Critical | CTO | Customer accounts, document metadata and analysis results |
| AST-04 | Customer document storage (S3) | Data store | Critical | CTO | Customer-uploaded documents, which may include personal data |
| AST-05 | Backup and log storage (S3) | Data store | High | CTO | Database snapshots, CloudTrail and application logs |
| AST-06 | AI model endpoints | Application | High | Engineering Lead | Hosted inference plus a third-party model API used for document analysis |
| AST-07 | Staff laptops (10 MacBooks) | Endpoint | High | Operations Manager | Remote-first staff; disk encryption and EDR enforced |
| AST-08 | Device management (MDM) | SaaS tool | Medium | Operations Manager | Enrolls laptops, enforces encryption and screen lock |
| AST-09 | GitHub | SaaS tool | Critical | Engineering Lead | Source code, CI pipeline and deployment |
| AST-10 | Google Workspace | SaaS tool | High | Operations Manager | Email, calendar, Drive and single sign-on |
| AST-11 | Slack | SaaS tool | Medium | Operations Manager | Team chat and incident channel |
| AST-12 | Notion | SaaS tool | Medium | Operations Manager | Internal wiki, runbooks and policies |
| AST-13 | 1Password | SaaS tool | High | CTO | Shared secrets and team passwords |
| AST-14 | Stripe | SaaS tool | High | Operations Manager | Billing and subscriptions (no card data stored by NovaCloud) |
| AST-15 | HubSpot | SaaS tool | Medium | Customer Success Manager | CRM with customer contact details |
| AST-16 | Linear | SaaS tool | Low | Engineering Lead | Issue tracking |
| AST-17 | Zoom | SaaS tool | Low | Operations Manager | Video meetings |

Classification summary: Critical 5, High 6, Medium 4, Low 2.

This inventory satisfies ISO/IEC 27001:2022 Annex A control **A.5.9** (inventory of information and other associated assets). A gap remains: it lists systems, not the information they hold. A data inventory with data owners is a planned improvement.

---

*NovaCloud AI Solutions is a fictional company. All people, systems, incidents, ratings and dates are examples created for skills practice and portfolio use. This is not legal advice or a compliance determination. Framework references are paraphrased pointers, so verify them against the source text before relying on them.*

Author: Augustine Ozor, AI Governance and Cybersecurity GRC. [GitHub](https://github.com/AugustineOzor) · [LinkedIn](https://www.linkedin.com/in/augustinetettehozor)
