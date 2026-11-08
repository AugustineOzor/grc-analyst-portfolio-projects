# Project 5: SOC 2 controls mapped to AWS

[← Repository home](../../README.md)

## Objective

Map SOC 2 Trust Services Criteria to real AWS settings, documenting how each control applies and what evidence proves it.

## Deliverables

| File | What it contains |
|---|---|
| [SOC 2 to AWS control mapping](soc2-aws-control-mapping.md) | 14 criteria mapped to AWS implementation, services, ISO controls and evidence names |
| [Evidence collection guide](evidence-guide.md) | Console path, CLI command, pass criteria and file name for 26 evidence items, plus safety and cost notes |

## Key results

- **14 criteria** across Security, Availability and Confidentiality (the brief asks for at least 10).
- Every control names the **AWS service**, a **verification command** and an **evidence file**.
- Each row ties back to an ISO 27001 control or a risk, so one set of evidence supports several frameworks.

## Honest status

The mapping is the design. The screenshots have **not** been captured, because they must come from a real sandbox account; the guide explains exactly how to take them. The [internal audit](../07-mock-internal-audit/README.md) raises this as a finding until the evidence exists.

## Improvements over the basic brief

- Added **CLI commands** so each control can be checked in text as well as by screenshot.
- Added a **cost and safety section** (budget alert, dummy data, redaction, clean-up) for the Free Tier.
- Made the **status explicit**, so the repo does not claim evidence it does not have.
- Cross-mapped to **ISO 27001** controls and **risks** so the work is reused.

## Skills shown

Control mapping · Cloud security (AWS) · Evidence design · SOC 2 and ISO crosswalks · Documentation

## Resume line

> Mapped 14 SOC 2 Trust Services Criteria to AWS services, with verification commands and an evidence plan of 26 items for a Free Tier sandbox, cross-referenced to ISO 27001 controls and the risk register.

---

*NovaCloud AI Solutions is a fictional company. All people, systems, incidents, ratings and dates are examples created for skills practice and portfolio use. This is not legal advice or a compliance determination. Framework references are paraphrased pointers, so verify them against the source text before relying on them.*

Author: Augustine Ozor, AI Governance and Cybersecurity GRC. [GitHub](https://github.com/AugustineOzor) · [LinkedIn](https://www.linkedin.com/in/augustinetettehozor)
