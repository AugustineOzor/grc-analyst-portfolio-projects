# Risk summary report

[← Project 2 README](README.md)

**For:** CEO and CTO · **Prepared by:** GRC Analyst · **Date:** November 2026

## Overall position

NovaCloud AI Solutions has 12 registered risks. Before controls, 3 are rated High and 9 Medium. With today's controls none are High, but 11 remain Medium, so the work is not finished. Completing the planned mitigations would bring 6 risks down to Low and leave 6 at Medium, which is acceptable for a company this size.

## The three highest risks

**1. R-01 Phishing leads to account takeover (inherent 16, current 12, target 8).** Staff email is the most likely way in. MFA is on, but the tabletop showed that attackers can capture sign-in sessions despite it. *Recommended:* run training and phishing simulations, and move admins and then all staff to security keys.

**2. R-02 Misconfigured S3 bucket exposes customer documents (inherent 15, current 10, target 5).** One public bucket could expose customer documents. *Recommended:* turn on S3 Block Public Access for the whole account, add an AWS Config rule that flags public buckets, and review infrastructure changes before they deploy.

**3. R-03 Leaked credentials or access keys in code (inherent 15, current 12, target 8).** A key committed to GitHub can give an attacker AWS access. *Recommended:* secret scanning with push protection, short-lived roles instead of access keys, and rotation of any key found.

## Decisions needed

1. Approve the owners and review dates in the [risk register](risk-register.md).
2. Fund the security keys for the team and the Config rules (low cost).
3. Accept that R-12 (dependence on a few key people) stays Medium until runbooks and shared on-call are in place.

---

*NovaCloud AI Solutions is a fictional company. All people, systems, incidents, ratings and dates are examples created for skills practice and portfolio use. This is not legal advice or a compliance determination. Framework references are paraphrased pointers, so verify them against the source text before relying on them.*

Author: Augustine Ozor, AI Governance and Cybersecurity GRC. [GitHub](https://github.com/AugustineOzor) · [LinkedIn](https://www.linkedin.com/in/augustinetettehozor)
