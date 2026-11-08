# Company profile: NovaCloud AI Solutions

NovaCloud AI Solutions is the fictional company used across all seven projects. It is deliberately small, so every control, risk and action in the repo is realistic for an early-stage startup preparing for its first certification.

| Item | Detail |
|---|---|
| Business | AI document analysis SaaS: customers upload contracts and reports, and the platform extracts key terms and summaries |
| Size | 10 employees, fully remote |
| Hosting | One AWS account (production), containerized services, PostgreSQL on RDS, documents in S3 |
| Data | Customer documents (may include personal data), account details, billing through Stripe |
| Customers | Small and mid-sized businesses in the US and EU |
| Regulatory drivers | GDPR and CCPA (personal data), customer security questionnaires, and a goal of ISO/IEC 27001:2022 certification |
| Compliance goal | Audit-ready for an ISO 27001 Stage 1 audit by Q3 2027, with SOC 2 Type I to follow |

## People and roles

| Role | Security responsibilities |
|---|---|
| CEO | Approves policies; privacy lead; owns the risk appetite |
| CTO | Acts as security lead; owns AWS, backups, logging and incident command |
| Engineering Lead | Code, CI, dependencies, vulnerability fixes |
| Engineers (3) | Build and operate the platform |
| Product Manager | Product requirements, customer-facing security features |
| Customer Success Manager | Customer communication and customer data exports |
| Operations Manager | Laptops, SaaS tools, vendors and onboarding |
| GRC Analyst | Runs the compliance program, risk register, vendor reviews and audits (the role this portfolio demonstrates) |

## Technology and asset summary

| ID | Asset | Type | Classification | Owner |
|---|---|---|---|---|
| AST-01 | AWS production account | Cloud account | Critical | CTO |
| AST-02 | API and worker services (ECS) | Application | Critical | Engineering Lead |
| AST-03 | PostgreSQL database (RDS) | Database | Critical | CTO |
| AST-04 | Customer document storage (S3) | Data store | Critical | CTO |
| AST-05 | Backup and log storage (S3) | Data store | High | CTO |
| AST-06 | AI model endpoints | Application | High | Engineering Lead |
| AST-07 | Staff laptops (10 MacBooks) | Endpoint | High | Operations Manager |
| AST-08 | Device management (MDM) | SaaS tool | Medium | Operations Manager |
| AST-09 | GitHub | SaaS tool | Critical | Engineering Lead |
| AST-10 | Google Workspace | SaaS tool | High | Operations Manager |
| AST-11 | Slack | SaaS tool | Medium | Operations Manager |
| AST-12 | Notion | SaaS tool | Medium | Operations Manager |
| AST-13 | 1Password | SaaS tool | High | CTO |
| AST-14 | Stripe | SaaS tool | High | Operations Manager |
| AST-15 | HubSpot | SaaS tool | Medium | Customer Success Manager |
| AST-16 | Linear | SaaS tool | Low | Engineering Lead |
| AST-17 | Zoom | SaaS tool | Low | Operations Manager |

## Project timeline

| Date | Milestone |
|---|---|
| 2 Nov 2026 | Baseline assessment starts (Project 1) |
| Early Nov 2026 | Risk register built (Project 2); first vendor assessed (Project 3) |
| 18 Nov 2026 | Incident response tabletop (Project 4) |
| Nov 2026 | SOC 2 to AWS mapping and evidence guide (Project 5) |
| 30 Nov 2026 | Dashboard snapshot (Project 6) |
| 8 to 10 Dec 2026 | Mock internal audit fieldwork (Project 7); report issued 11 Dec 2026 |

---

*NovaCloud AI Solutions is a fictional company. All people, systems, incidents, ratings and dates are examples created for skills practice and portfolio use. This is not legal advice or a compliance determination. Framework references are paraphrased pointers, so verify them against the source text before relying on them.*

Author: Augustine Ozor, AI Governance and Cybersecurity GRC. [GitHub](https://github.com/AugustineOzor) · [LinkedIn](https://www.linkedin.com/in/augustinetettehozor)
