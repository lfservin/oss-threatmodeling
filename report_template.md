# Security Assessment Report Template

*[Use this template to document the results of a security assessment, such as penetration tests, application security reviews, etc. It draws on established testing and reporting frameworks where appropriate and practical.*

*Text in italic square brackets is guidance for you. Delete it before finalizing. Regular-font text is part of the report, so keep and adapt it. Rename the generic title above to match your assessment.*

*This template was [created by Lenny Zeltser](https://zeltser.com/security-assessment-report-template) under the [Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/) (CC BY 4.0). The license covers the template. Any report you produce with it is yours.]*

*[Handling: Mark the report's sensitivity using your data classification, and store and send it securely. For external sharing, [TLP](https://www.first.org/tlp/) is common.]*

*[Reader Profile: Internal reports (for your own organization) can assume shared context and drop the disclaimer and attestation. External reports (a client's environment) typically need full scope, rules of engagement, the [Limitations and Disclaimer](#limitations-and-disclaimer) section, and an attestation if the engagement calls for one.]*

## Contents

*[Update this list as you add or remove sections, including the optional ones you don't use.]*

- [Executive Summary](#executive-summary)
- [Assessment Scope](#assessment-scope)
- [Findings Summary](#findings-summary)
- [Detailed Findings](#detailed-findings)
- [Remediation Priorities](#remediation-priorities)
- [Attack Path Narrative (Optional)](#attack-path-narrative-optional)
- [Detection and Response Observations (Optional)](#detection-and-response-observations-optional)
- [Methodology](#methodology)
- [Limitations and Disclaimer](#limitations-and-disclaimer)
- [Appendices](#appendices)
- [About this Report](#about-this-report)

## Executive Summary

*[Write for a busy, non-technical reader. This is the most widely shared part of the report, so it must stand on its own. Communicate the overall posture, the top conclusions and recommendations, and any real strengths.*

*[Bulleted takeaways are a good idea; for example:*

- *What you assessed and why.*
- *Your overall security posture or risk perspective.*
- *The most significant weakness, and what it could lead to.*
- *The key recommendation, and its urgency.]*

*[If relevant to your engagement, also say whether you met the objectives, whether defenders detected the activity, and how long it went unnoticed.]*

*[For an objective-based engagement such as a red team, an Objectives and Outcomes table makes the result scannable. Delete it otherwise.]*

| Objective | Outcome | Notes |
|---|---|---|
| *[The goal, such as reach Domain Admin or access the customer database.]* | *[Met, Partially met, or Not met.]* | *[How far you got, and the key evidence or finding.]* |

## Assessment Scope

*[Don't assume the reader knows the engagement's scope so outline it here.]*

|  |  |
|---|---|
| **Objectives** | *[The business and technical goals.]* |
| **What Was Tested** | *[The applications, processes, and infrastructure in scope. Scope by what an attacker could reach, and name adjacent systems the work might touch.]* |
| **What Was Excluded** | *[Components left out of scope, and why.]* |
| **Timing** | *[The dates, so readers know how current the findings are.]* |
| **Constraints** | *[Limits on time, people, expertise, or scenario, such as "20 hours, black-box, no source access."]* |

*[For external engagements, add the rules of engagement and other pertinent details. Be brief.]*

## Findings Summary

*[List the findings at a glance, ordered by decreasing severity. Add a Type column, such as access control or cryptography, to show patterns. Add a Status column when you're tracking fixes or retesting.]*

| ID | Finding | Severity | Affected Asset |
|---|---|---|---|
|  |  |  |  |

**Strengths:** *[Note what the organization does well, and systemic observations the findings can't capture, such as code maturity or controls that held up. Naming genuine strengths builds trust and balances the report. For a code or application review, consider a short per-area maturity summary. A small table works well: the areas you assessed (such as access control, cryptography, data handling, and configuration), a rating for each (such as strong, adequate, or weak), and a brief note.]*

*[Optionally, a severity-distribution chart or a likelihood-by-impact heat map can show patterns the table can't.]*

## Detailed Findings

*[One block per finding, in summary order. The core fields below are enough, so add the rest only when they help. Number and caption figures, reference them by number, and keep heavy evidence in an appendix.]*

### [Finding title that states the weakness and its outcome]

|  |  |
|---|---|
| **Finding ID** | *[For example, F01.]* |
| **Severity** | *[The level from your scale.]* |
| **Affected Asset(s)** | *[The specific asset, precise enough that the reader can locate it. Match the form to the work: a file path and commit for code, a URL or parameter for web, an account, region, and resource ID for cloud, a hostname or address for infrastructure. If a finding affects many assets, give the count and point to the full list in an appendix or attached file.]* |
| **Description** | *[What the weakness is.]* |
| **Significance** | *[Why it matters to this organization, given exposure, compensating controls, and the affected asset's value. State this context plainly, without scare language.]* |
| **Validation** | *[How the reader can confirm the weakness, with steps or evidence.]* |
| **Remediation** | *[How to fix it, and how to confirm the fix. If the steps are long, summarize and link to a separate document.]* |

*[Add a row only when it applies:*

- *Exploit Scenario: a short, concrete account of how an attacker turns this weakness into impact, distinct from Significance. Add it when the path isn't obvious from the description.*
- *Status: Open, Remediated, Risk accepted, or Retested-pass.*
- *Confirmation: Confirmed, or Potential for unverified automated output.*
- *Likelihood and Impact: the basis for the severity.*
- *Type: a category such as access control or cryptography.*
- *Difficulty: how hard the weakness is to exploit, useful for code reviews.*
- *Tools Used: the tools or manual technique that produced the finding.*
- *[CVSS](https://www.first.org/cvss/): the base vector and score, used as one input to the rating.*
- *References: CVE, CWE, OWASP, or ATT&CK identifiers.]*

*[Repeat the block above for each finding. In a red team report, these items may be systemic lessons rather than severity-ranked weaknesses. The [Attack Path Narrative](#attack-path-narrative-optional) below tells the story.]*

## Remediation Priorities

*[Use this section to put the recommended fixes in priority order. Base the order on the risk-adjusted severity. Where you understand the team's capacity and operational dynamics, factor those in too, such as putting a couple of quick wins first. Keep each row short and reference the finding by ID. The finding above already has the full fix. Leave Owner for the organization if you don't know internal owners.]*

| Priority | Finding(s) | Recommended Action | Effort | Owner |
|---|---|---|---|---|
|  |  |  |  |  |

*[Some recommendations aren't tied to a single finding, such as adopting behavior-based detection. Add these as their own rows.]*

## Attack Path Narrative (Optional)

*[Keep this section for a red team or adversary-emulation engagement, when readers want the story behind the findings. It follows the findings so readers reach the results first. Delete it otherwise.]*

This section describes the path through the environment, from initial access to the objective.

*[Tell the story in whatever order serves the reader, naming the technique at each step and referencing [MITRE ATT&CK](https://attack.mitre.org) inline, for example T1078 Valid Accounts.]*

## Detection and Response Observations (Optional)

*[Keep this section for a red team engagement, or any assessment that tested detection and response. Delete it otherwise.]*

This section records what the organization's defenders detected, what they missed, and how quickly they responded.

*[Be specific about the time to detect, which controls or alerts fired, and where activity went unnoticed. Tie observations to the steps in the [Attack Path Narrative](#attack-path-narrative-optional).]*

## Methodology

*[With your methodology, the reader can follow how you reached your findings and recommendations. A clear, consistent approach is also why they trust the results.]*

This section describes our approach to performing the assessment and prioritizing the findings.

**Assessment Type:** *[Explain and name it the way that'll resonate with the reader, such as penetration test, vulnerability assessment, red team, etc. Definitions vary, so clarify what the work did and didn't do.]*

**Standards and Frameworks:** *[What informed the work, such as the [OWASP testing guides](https://owasp.org/www-project-web-security-testing-guide/), [NIST SP 800-115](https://csrc.nist.gov/pubs/sp/800/115/final), or [PCI DSS](https://www.pcisecuritystandards.org/). Relate a proprietary approach to methods readers know. For a red team engagement, MITRE ATT&CK is well-recognized.]*

**Tools and Techniques:** *[The automated tools and manual steps, including any autonomous or AI-driven testing, and when you used each.]*

**Severity and Prioritization:** *[Rate findings by risk to this organization rather than raw technical severity alone. Treat a base score such as CVSS as one input, and adjust it for exposure, mitigating controls, data sensitivity, and asset value. You may rank a finding above or below its base score after weighing this context. The table below is one example. Use whatever rating approach fits, define what each rating means, and explain how you ordered the findings.]*

| Level | Criteria | What It Implies |
|---|---|---|
| Critical |  | Fix immediately. |
| High |  | Address as soon as possible. |
| Medium |  | Plan to address in the near term. |
| Low |  | Address after higher-severity items. |

*[Add your own analysis and prioritization on top of any tool output.]*

## Limitations and Disclaimer

*[Keep this section for external engagements, and omit it for internal reports. State what the assessment did not cover, any false-positive caveats, and the point-in-time nature of the results. The engagement contract usually covers the legal terms, such as authorized use.]*

## Appendices

*[Optional. Use appendices for reference material that supports the findings but would clutter the body. Include only what a reader would actually open. Raw tool output is usually for the assessor, so add it here (or as a separate file) only if a reader needs it. Common examples:*

- *Evidence and figures referenced in the findings.*
- *Retest results, once the organization has remediated.*
- *For red team work, the full ATT&CK technique set, such as a Navigator layer.*
- *For cloud reviews, a benchmark mapping.]*

## About this Report

|  |  |
|---|---|
| **Report Title** |  |
| **Assessor(s) and Organization** |  |
| **Report Date** |  |
| **Handling / Classification** | *[The marking from the top of the report.]* |
| **Follow-Up Contact** | *[Who to contact with questions.]* |

### Report Changelog (Optional)

*[Keep this table for formal or externally distributed reports that go through drafts and a post-retest revision, and delete it otherwise.]*

| Date | Author | Change Description |
|---|---|---|
|  |  |  |
