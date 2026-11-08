# Project 4: Incident response plan, tested

[← Repository home](../../README.md)

## Objective

Write a complete incident response plan covering roles, detection, containment, eradication, recovery and lessons learned, then test it with a tabletop simulation of a phishing-led data leak and document the result.

## Deliverables

| File | What it contains |
|---|---|
| [Incident response plan](incident-response-plan.md) | Purpose, severity levels, roles, the seven required sections, communications and notification matrix, contact list |
| [Tabletop exercise](tabletop-exercise.md) | Scenario, injects with expected and actual responses, steps documented (identify, respond, communicate), gaps and actions |
| [Incident report (completed)](incident-report.md) | Report on the exercise with timeline, impact, root cause and remediation |
| [Incident report template](incident-report-template.md) | Blank reusable template |
| [Timeline chart](assets/tabletop-timeline.png) | Visual timeline of the exercise |

## Key results

- A plan short enough to use in an emergency, aligned to **ISO/IEC 27035** and ISO 27001 controls A.5.24 to A.5.28.
- The tabletop found **5 gaps**, each turned into an owned, dated action (ACT-06 to ACT-10).
- Main lesson: MFA by authenticator app did not stop a phishing attack that captures the session.

## Improvements over the basic brief

- Used a scenario where **MFA is already on**, because that tests a realistic weakness rather than a gap everyone expects.
- Added a **notification matrix** (customers, authorities, US states) and the 72-hour duties as a processor.
- Wrote **expected versus actual responses** for each inject, so the gaps are evidence, not opinion.
- Fed the gaps into the shared action list, the [dashboard](../06-compliance-dashboard/README.md) and the [internal audit](../07-mock-internal-audit/README.md).

## Skills shown

Incident response planning · Tabletop facilitation · Process documentation · Breach notification · Root cause analysis

## Resume line

> Wrote an ISO 27035-aligned incident response plan and ran a phishing tabletop that exposed 5 gaps (MFA, alerting, on-call, notification, data sprawl), each converted into an owned corrective action with a due date.

---

*NovaCloud AI Solutions is a fictional company. All people, systems, incidents, ratings and dates are examples created for skills practice and portfolio use. This is not legal advice or a compliance determination. Framework references are paraphrased pointers, so verify them against the source text before relying on them.*

Author: Augustine Ozor, AI Governance and Cybersecurity GRC. [GitHub](https://github.com/AugustineOzor) · [LinkedIn](https://www.linkedin.com/in/augustinetettehozor)
