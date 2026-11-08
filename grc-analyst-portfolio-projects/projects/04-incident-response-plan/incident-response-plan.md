# Incident response plan

[← Project 4 README](README.md)

| Item | Detail |
|---|---|
| Document | IRP-001, version 1.0 |
| Owner | CTO (incident commander) |
| Approved by | CEO (approval pending) |
| Review | Every 12 months, and after every serious incident or tabletop |
| Aligned to | ISO/IEC 27035 (plan and prepare; detect and report; assess and decide; respond; learn lessons) and ISO/IEC 27001:2022 A.5.24 to A.5.28 |

## 1. Purpose

To make sure NovaCloud AI Solutions detects security incidents quickly, limits the harm, recovers safely, meets its legal and contractual duties to customers, and learns from each event. The plan is short on purpose: a 10-person team must be able to read it in an emergency.

## 2. Scope and definitions

The plan covers any event that threatens the confidentiality, integrity or availability of NovaCloud systems, customer data or staff accounts.

| Term | Meaning |
|---|---|
| Event | Anything unusual that might affect security, such as a strange login alert |
| Incident | An event confirmed or likely to cause harm |
| Incident commander | The person who leads the response and makes decisions |

| Severity | Examples | Acknowledge | Declare | Updates |
|---|---|---|---|---|
| 🟥 High | Customer data accessed or exposed; production compromised; ransomware | 15 minutes | Within 1 hour | Every 2 hours |
| 🟨 Medium | Single account compromised with no data accessed; malware on one laptop | 1 hour | Within 4 hours | Every 8 hours |
| 🟩 Low | Spam, failed logins, a reported suspicious email with no click | Next business day | Not needed | As needed |

If you are unsure, treat it as the higher severity.

## 3. Roles

| Role | Who | Responsibilities |
|---|---|---|
| Incident commander | CTO | Declares the incident, leads decisions, approves containment |
| Deputy commander | Engineering Lead | Takes over if the CTO is unavailable; leads technical investigation |
| Coordinator and scribe | GRC Analyst | Keeps the timeline, tracks actions, prepares the report |
| Communications lead | CEO | Approves messages to customers, regulators and the public |
| Customer lead | Customer Success Manager | Sends approved messages and answers customer questions |
| Endpoint and access | Operations Manager | Locks accounts, wipes or isolates laptops |
| Legal advisor | External counsel on retainer | Advises on notification duties; called for High severity |
| All staff | Everyone | Report anything suspicious at once through the security channel |

## 4. Detection and reporting

- **Sources:** staff reports, Google and AWS sign-in alerts, GuardDuty and CloudTrail alerts, EDR alerts, customer or vendor reports.
- **How to report:** post in the private security channel and tag the CTO. Out of hours, phone the on-call number in the contact list.
- **First 15 minutes:** the first responder records the time, what was seen, and who reported it, then asks the commander to classify the severity.
- Staff are never blamed for reporting quickly, including after a click.

## 5. Assessment and decision

The commander decides within the time in the severity table: Is it real? What data or systems are affected? Is it still going on? A **High** incident is formally declared, the incident channel is opened, and the coordinator starts the timeline.

## 6. Containment

Stop the harm before fixing the cause.

| Situation | Containment steps |
|---|---|
| Compromised user account | Suspend the account, revoke all sessions and tokens, reset the password and security keys, remove mail forwarding rules |
| Compromised AWS key or role | Disable or rotate the key, attach a deny policy, review CloudTrail for what it did |
| Infected laptop | Isolate it with EDR or MDM, do not wipe it until evidence is saved |
| Exposed storage | Turn on Block Public Access, remove public permissions, check access logs |

Save evidence first: export audit logs, take disk or snapshot copies, and note who handled what. Do not delete anything without the commander's approval.

## 7. Eradication

Find and remove the cause: delete malicious rules, apps and files, close the entry route (for example the phishing domain), patch the weakness, and confirm no other accounts or devices are affected. Check for persistence such as new users, access keys or OAuth app grants.

## 8. Recovery

Restore from known-good sources, return users to service in stages, watch the affected systems closely for 7 days, and confirm with the commander before closing. Recovery of production data uses the database backup and restore steps once they have been tested (see action ACT-11).

## 9. Communications and notification

| Audience | When | Who decides | Who sends |
|---|---|---|---|
| Staff | As soon as staff action is needed | Commander | Commander |
| Affected customers | Without undue delay, and within **72 hours** of becoming aware, as the contracts require | CEO with external counsel | Customer Success Manager |
| Data protection authorities | The customer, as controller, notifies the authority within 72 hours of becoming aware (GDPR Art. 33(1)); NovaCloud as processor tells the customer without undue delay (Art. 33(2)) | Customer | Customer |
| US state regulators and individuals | As state breach laws require | CEO with external counsel | CEO |
| Insurer, if any | As the policy states | CEO | CEO |

Use the customer notice template (action ACT-07). Say what is known, what is not, what customers should do, and when the next update will come. One person speaks for the company.

## 10. Lessons learned

Hold a blameless review within **5 working days** of closing a High incident (and after every tabletop). Cover the timeline, what worked, what did not, root cause and contributing factors, and agree actions with owners and dates. Track them on the shared action list, and update this plan.

## 11. Testing and maintenance

Run a tabletop exercise at least once a year and after any major change. Review the contact list quarterly. Review the plan every 12 months.

## 12. Contact list

| Role | Name | Phone | Backup |
|---|---|---|---|
| CTO (commander) | [name] | [phone] | Engineering Lead |
| Engineering Lead | [name] | [phone] | CTO |
| CEO | [name] | [phone] | CTO |
| Operations Manager | [name] | [phone] | CEO |
| External counsel | [firm] | [phone] | n/a |
| AWS support | Account portal | n/a | n/a |

*The after-hours rota is still to be set up (action ACT-06).*

---

*NovaCloud AI Solutions is a fictional company. All people, systems, incidents, ratings and dates are examples created for skills practice and portfolio use. This is not legal advice or a compliance determination. Framework references are paraphrased pointers, so verify them against the source text before relying on them.*

Author: Augustine Ozor, AI Governance and Cybersecurity GRC. [GitHub](https://github.com/AugustineOzor) · [LinkedIn](https://www.linkedin.com/in/augustinetettehozor)
