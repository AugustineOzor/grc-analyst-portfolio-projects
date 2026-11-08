# SOC 2 to AWS control mapping

[← Project 5 README](README.md)

Mapping of 14 SOC 2 Trust Services Criteria to the AWS environment of NovaCloud AI Solutions. The criteria come from the Security (Common Criteria CC1 to CC9), Availability (A1) and Confidentiality (C1) categories of the AICPA Trust Services Criteria (2017, with the 2022 revised points of focus).

> **Status:** this is the *design* of the control and the evidence plan. The screenshots named in the last column are listed in the [evidence guide](evidence-guide.md) and are still to be captured from a real AWS Free Tier account (action ACT-18). Nothing here claims that a configuration has been proven.

## Mapping

| Control ID | Criterion | Requirement | Implementation in AWS | AWS services | Related ISO 27001 control or risk | Evidence screenshot (to capture) |
|---|---|---|---|---|---|---|
| CC6.1 | Logical access security | Restrict access to systems and data to authorized users, using access security software and architecture. | IAM Identity Center with Google sign-in and MFA enforced; no IAM users with console passwords; S3 Block Public Access on for the whole account. | IAM Identity Center, IAM, S3 | A.5.15, A.8.5 | `CC6.1-01-identity-center-mfa.png`, `CC6.1-02-s3-block-public-access.png` |
| CC6.2 | User registration and removal | Authorize users before access is granted, and remove access when it is no longer needed. | Joiners are added to IAM Identity Center groups through a ticket; leavers are removed within 24 hours; access is reviewed every quarter. | IAM Identity Center | A.5.15 | `CC6.2-01-groups-and-assignments.png`, `CC6.2-02-offboarding-ticket.png` |
| CC6.3 | Role-based access and least privilege | Grant access by role, with least privilege and separation of duties. | Permission sets per role (read-only, developer, admin). Admin is a time-limited assignment, not standing. No shared accounts. | IAM Identity Center, IAM Access Analyzer | A.8.2, A.5.15 | `CC6.3-01-permission-sets.png`, `CC6.3-02-access-analyzer.png` |
| CC6.6 | Boundary protection | Protect the system against threats from outside its boundaries. | Database and workers sit in private subnets; security groups allow only required ports; no rule opens a database or SSH to the whole internet. | VPC, security groups | A.5.23; R-02 | `CC6.6-01-security-groups.png` |
| CC6.7 | Protection of data in transit | Restrict and protect the transmission of information. | Load balancer accepts HTTPS only with a TLS 1.2 or higher policy; S3 bucket policy denies requests that do not use secure transport; the database requires SSL. | ACM, load balancer, S3, RDS | A.8.24 | `CC6.7-01-alb-https-listener.png`, `CC6.7-02-s3-secure-transport-policy.png` |
| CC6.8 | Malicious software | Prevent or detect unauthorized or malicious software. | Container images are scanned on push; GuardDuty is enabled; laptops run EDR (managed outside AWS). | ECR, GuardDuty | A.8.7 | `CC6.8-01-ecr-scan-on-push.png`, `CC6.8-02-guardduty-enabled.png` |
| CC7.1 | Detection of changes and vulnerabilities | Use detection and monitoring to find configuration changes and new vulnerabilities. | AWS Config records changes and runs managed rules (public buckets, MFA, encryption); Inspector scans container images; findings are reviewed weekly. | AWS Config, Inspector | A.8.8; R-04 | `CC7.1-01-config-rules.png`, `CC7.1-02-inspector-findings.png` |
| CC7.2 | Monitoring for anomalies | Monitor system components for anomalies that may indicate attacks or failures. | A multi-region CloudTrail trail with log file validation writes to a protected bucket. CloudWatch alarms fire on root sign-in, console sign-in without MFA and IAM policy changes. | CloudTrail, CloudWatch | A.8.15 | `CC7.2-01-cloudtrail-trail.png`, `CC7.2-02-cloudwatch-alarms.png` |
| CC7.3 | Evaluation of security events | Evaluate security events to decide whether they are incidents. | GuardDuty, Config and CloudWatch alerts go through EventBridge to SNS and a Slack channel. Each alert is triaged and logged with a severity from the incident response plan. | EventBridge, SNS | A.5.24 | `CC7.3-01-eventbridge-rule.png`, `CC7.3-02-triage-log.png` |
| CC7.4 | Incident response | Respond to identified security incidents with a defined program. | The incident response plan and tabletop report (Project 4). AWS runbook: swap an instance to a quarantine security group and disable a compromised access key. | EC2, IAM | A.5.24 | `CC7.4-01-ir-plan-and-tabletop.pdf`, `CC7.4-02-quarantine-sg.png` |
| CC7.5 | Recovery from incidents | Recover from security incidents. | Quarterly restore test: restore the latest RDS snapshot into a new instance, check the data, record the time taken and compare it with the recovery target. | RDS, AWS Backup | A.8.13, A.5.30; R-07 | `CC7.5-01-restore-test-log.png` |
| CC8.1 | Change management | Authorize, design, test and approve changes before they are made. | Branch protection on GitHub (pull request, one approval, passing checks); deployments run in CI using a short-lived OIDC role, with no stored AWS keys; infrastructure as code with a reviewed plan. | IAM OIDC provider, CloudFormation | A.8.32; R-03 | `CC8.1-01-branch-protection.png`, `CC8.1-02-deploy-role-oidc.png` |
| A1.2 | Availability: backup and recovery infrastructure | Maintain environmental protections, backup and recovery infrastructure. | RDS automated backups kept 7 days with Multi-AZ; an AWS Backup plan copies to a second region; S3 versioning is on for customer documents. | RDS, AWS Backup, S3 | A.8.13 | `A1.2-01-rds-backup-config.png`, `A1.2-02-backup-plan.png` |
| C1.1 | Confidentiality: protection of confidential information | Identify and maintain confidential information, and protect it. | S3 and RDS are encrypted with KMS keys with rotation on. Resources are tagged with a data classification so owners and handling rules are clear. | KMS, S3, RDS | A.8.24, A.5.9 | `C1.1-01-kms-rotation.png`, `C1.1-02-resource-tags.png` |

## Coverage

| Category | Criteria mapped |
|---|---|
| Security (common criteria) | CC6.1, CC6.2, CC6.3, CC6.6, CC6.7, CC6.8, CC7.1, CC7.2, CC7.3, CC7.4, CC7.5, CC8.1 |
| Availability | A1.2 |
| Confidentiality | C1.1 |

CC1 to CC5 and CC9 (control environment, communication, risk assessment, monitoring and risk mitigation) are organizational rather than cloud settings. They are covered by the policies, risk register and internal audit in the other projects.

## Shared responsibility

AWS is responsible for security *of* the cloud (data centers, hardware, the managed service itself). NovaCloud AI Solutions is responsible for security *in* the cloud: identities, configuration, data, and the way the services are used. This mapping covers the second part. AWS's own SOC 2 report covers the first.

## Linking to the rest of the portfolio

- Each row links to an ISO 27001 control in the [control matrix](../01-mini-compliance-program/03-iso-27001-control-matrix.md) or a risk in the [risk register](../02-risk-register/risk-register.md).
- The evidence collection action is tracked as ACT-18 in the [dashboard](../06-compliance-dashboard/README.md), and the [internal audit](../07-mock-internal-audit/README.md) reports the gap while the evidence is missing.

---

*NovaCloud AI Solutions is a fictional company. All people, systems, incidents, ratings and dates are examples created for skills practice and portfolio use. This is not legal advice or a compliance determination. Framework references are paraphrased pointers, so verify them against the source text before relying on them.*

Author: Augustine Ozor, AI Governance and Cybersecurity GRC. [GitHub](https://github.com/AugustineOzor) · [LinkedIn](https://www.linkedin.com/in/augustinetettehozor)
