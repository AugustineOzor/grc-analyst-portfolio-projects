# Evidence collection guide

[← Project 5 README](README.md)

How to capture the evidence for the [mapping](soc2-aws-control-mapping.md) in a sandbox AWS account. There are **26 evidence items** across 14 criteria.

## Before you start

1. **Use a sandbox account** (AWS Free Tier), never a real production account.
2. **Set a budget alert** (for example 5 USD) in AWS Budgets. Some services here (AWS Config, Inspector, and GuardDuty after its trial) can charge. Check current pricing before enabling them.
3. **Use dummy data only.** Do not upload real documents or personal data.
4. **Redact before saving:** account IDs, email addresses, access key IDs and names.
5. **Clean up** when finished: delete test resources, the restored database and any extra trails or recorders.

## Folder and naming

```
SOC 2 Artifacts/
├── CC6/   CC6.1-01-identity-center-mfa.png ...
├── CC7/   CC7.2-01-cloudtrail-trail.png ...
├── CC8/   CC8.1-01-branch-protection.png ...
├── A1/    A1.2-01-rds-backup-config.png
└── C1/    C1.1-01-kms-rotation.png
```

Name each file `<criterion>-<number>-<what-it-shows>.png`. Include the date and time in the screenshot (a visible clock or the console timestamp) so the evidence is dated.

## Capture steps by criterion

Each row gives the console location, an AWS CLI command that returns the same facts in text (useful as a second form of evidence), what the screenshot must show to count as passing, and the file name.

### CC6.1: Logical access security

| Where to look (console) | Command to run | What the screenshot must show | Save as |
|---|---|---|---|
| IAM Identity Center > Settings > Authentication | `aws sso-admin list-instances` | MFA required for all users; identity source shown | `CC6.1-01-identity-center-mfa.png` |
| S3 > Block Public Access settings for this account | `aws s3control get-public-access-block --account-id <ACCOUNT_ID>` | All four Block Public Access settings on | `CC6.1-02-s3-block-public-access.png` |

### CC6.2: User registration and removal

| Where to look (console) | Command to run | What the screenshot must show | Save as |
|---|---|---|---|
| IAM Identity Center > Groups and AWS accounts | `aws identitystore list-group-memberships --identity-store-id <ID> --group-id <GROUP_ID>` | Group memberships match the current staff list | `CC6.2-01-groups-and-assignments.png` |
| Ticket system | n/a | A sample offboarding ticket showing access removed within 24 hours (redact names) | `CC6.2-02-offboarding-ticket.png` |

### CC6.3: Role-based access and least privilege

| Where to look (console) | Command to run | What the screenshot must show | Save as |
|---|---|---|---|
| IAM Identity Center > Permission sets | `aws sso-admin list-permission-sets --instance-arn <ARN>` | Role-based permission sets; no one assigned admin permanently | `CC6.3-01-permission-sets.png` |
| IAM > Access Analyzer | `aws accessanalyzer list-analyzers` | An analyzer is active and findings are reviewed | `CC6.3-02-access-analyzer.png` |

### CC6.6: Boundary protection

| Where to look (console) | Command to run | What the screenshot must show | Save as |
|---|---|---|---|
| VPC > Security groups | `aws ec2 describe-security-groups --query "SecurityGroups[?IpPermissions[?IpRanges[?CidrIp=='0.0.0.0/0']]].GroupId"` | No security group exposes 22 or 5432 to 0.0.0.0/0 | `CC6.6-01-security-groups.png` |

### CC6.7: Protection of data in transit

| Where to look (console) | Command to run | What the screenshot must show | Save as |
|---|---|---|---|
| EC2 > Load balancers > Listeners | `aws elbv2 describe-listeners --load-balancer-arn <ARN>` | HTTPS listener with a TLS 1.2 or higher security policy; HTTP redirects to HTTPS | `CC6.7-01-alb-https-listener.png` |
| S3 > Bucket > Permissions > Bucket policy | `aws s3api get-bucket-policy --bucket <BUCKET>` | Policy denies when aws:SecureTransport is false | `CC6.7-02-s3-secure-transport-policy.png` |

### CC6.8: Malicious software

| Where to look (console) | Command to run | What the screenshot must show | Save as |
|---|---|---|---|
| ECR > Repositories > Scanning configuration | `aws ecr describe-repositories --query 'repositories[].{name:repositoryName,scan:imageScanningConfiguration.scanOnPush}'` | scanOnPush is true for every repository | `CC6.8-01-ecr-scan-on-push.png` |
| GuardDuty > Summary | `aws guardduty list-detectors` | A detector is enabled in each region in use | `CC6.8-02-guardduty-enabled.png` |

### CC7.1: Detection of changes and vulnerabilities

| Where to look (console) | Command to run | What the screenshot must show | Save as |
|---|---|---|---|
| AWS Config > Rules | `aws configservice describe-configuration-recorders` | Recorder on; rules for public S3, root MFA and encryption with their compliance state | `CC7.1-01-config-rules.png` |
| Inspector > Findings | `aws inspector2 list-findings --max-results 5` | Scanning enabled and a sample of findings with owners | `CC7.1-02-inspector-findings.png` |

### CC7.2: Monitoring for anomalies

| Where to look (console) | Command to run | What the screenshot must show | Save as |
|---|---|---|---|
| CloudTrail > Trails | `aws cloudtrail get-trail-status --name <TRAIL>` | Trail is logging, multi-region, log validation on | `CC7.2-01-cloudtrail-trail.png` |
| CloudWatch > Alarms | `aws cloudwatch describe-alarms --query "MetricAlarms[].AlarmName"` | Alarms exist for root use, no-MFA sign-in and IAM changes | `CC7.2-02-cloudwatch-alarms.png` |

### CC7.3: Evaluation of security events

| Where to look (console) | Command to run | What the screenshot must show | Save as |
|---|---|---|---|
| EventBridge > Rules | `aws events list-rules` | A rule routes GuardDuty findings to an SNS topic | `CC7.3-01-eventbridge-rule.png` |
| Triage log | n/a | A sample triage entry with time, severity and outcome (redact details) | `CC7.3-02-triage-log.png` |

### CC7.4: Incident response

| Where to look (console) | Command to run | What the screenshot must show | Save as |
|---|---|---|---|
| Repository | n/a | The approved incident response plan and tabletop report | `CC7.4-01-ir-plan-and-tabletop.pdf` |
| EC2 > Security groups | `aws ec2 describe-security-groups --filters Name=group-name,Values=quarantine` | A quarantine group with no inbound or outbound rules | `CC7.4-02-quarantine-sg.png` |

### CC7.5: Recovery from incidents

| Where to look (console) | Command to run | What the screenshot must show | Save as |
|---|---|---|---|
| RDS > Snapshots > Restore | `aws rds describe-db-snapshots --db-instance-identifier <DB>` | Snapshot list and the restored instance, plus a written log of time taken | `CC7.5-01-restore-test-log.png` |

### CC8.1: Change management

| Where to look (console) | Command to run | What the screenshot must show | Save as |
|---|---|---|---|
| GitHub > Settings > Branches (outside AWS) | `gh api repos/<ORG>/<REPO>/branches/main/protection` | Pull request reviews and status checks required | `CC8.1-01-branch-protection.png` |
| IAM > Identity providers | `aws iam list-open-id-connect-providers` | GitHub OIDC provider and a deploy role with a restricted trust policy | `CC8.1-02-deploy-role-oidc.png` |

### A1.2: Availability: backup and recovery infrastructure

| Where to look (console) | Command to run | What the screenshot must show | Save as |
|---|---|---|---|
| RDS > Databases > Maintenance and backups | `aws rds describe-db-instances --query 'DBInstances[].{id:DBInstanceIdentifier,retention:BackupRetentionPeriod,enc:StorageEncrypted,multiAZ:MultiAZ}'` | Retention of 7 days or more, Multi-AZ true, encrypted true | `A1.2-01-rds-backup-config.png` |
| AWS Backup > Backup plans | `aws backup list-backup-plans` | A plan with a cross-region copy rule | `A1.2-02-backup-plan.png` |

### C1.1: Confidentiality: protection of confidential information

| Where to look (console) | Command to run | What the screenshot must show | Save as |
|---|---|---|---|
| KMS > Customer managed keys | `aws kms get-key-rotation-status --key-id <KEY_ID>` | Automatic key rotation enabled | `C1.1-01-kms-rotation.png` |
| S3 > Bucket > Properties > Tags | `aws s3api get-bucket-tagging --bucket <BUCKET>` | A DataClassification tag on each data bucket | `C1.1-02-resource-tags.png` |


## Evidence log (complete as you go)

| File | Criterion | Captured on | Captured by | Passes? | Notes |
|---|---|---|---|---|---|
| | | | | | |

**Status at 30 Nov 2026:** 0 of 26 items captured. Action ACT-18, due 31 December 2026.

---

*NovaCloud AI Solutions is a fictional company. All people, systems, incidents, ratings and dates are examples created for skills practice and portfolio use. This is not legal advice or a compliance determination. Framework references are paraphrased pointers, so verify them against the source text before relying on them.*

Author: Augustine Ozor, AI Governance and Cybersecurity GRC. [GitHub](https://github.com/AugustineOzor) · [LinkedIn](https://www.linkedin.com/in/augustinetettehozor)
