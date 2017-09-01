# Kovri Vulnerability Response Process

## Preamble

Researchers/Hackers: while you research/hack, we ask that you please refrain from committing the following:
- Denial of Service / Active exploiting against the network
- Social Engineering of Monero staff or contractors
- Any physical or electronic attempts against Monero community property and/or data centers

## I. Point of Contact for Security Issues

```
anonimal at mail.i2p
anonimal at i2pmail.org
PGP key fingerprint = 1218 6272 CD48 E253 9E2D  D29B 66A7 6ECF 9144 09F1
```

## II. Security Response Team

- anonimal
- fluffypony

## III. Incident Response

1. Researcher submits report via one or both of two methods:
    - a. Email
    - b. [HackerOne](https://hackerone.com/monero)

2. Response Team designates a Response Manager who is in charge of the particular report based on availability and/or knowledge-set

3. In no more than 3 working days, Response Team should gratefully respond to researcher using only encrypted, secure channels

4. Response Manager makes inquiries to satisfy any needed information to confirm if submission is indeed a vulnerability
    - a. If submission proves to be vulnerable, proceed to next step
    - b. If not vulnerable:
      - i. Response Manager responds with reasons why submission is not a vulnerability
      - ii. Response Manager moves discussion to a new or existing ticket on GitHub if necessary

5. If over email, Response Manager opens a HackerOne issue for new submission

6. Establish severity of vulnerability:
    - a. HIGH: effects network as a whole, has potential to break entire network or is on a scale of great catastrophe
    - b. MEDIUM: effects individual routers, or must be carefully exploited
    - c. LOW: Is not easily exploitable

7. Respond according to the severity of the vulnerability:
    - a. HIGH severities must be notified on website and reddit /r/Kovri within 3 working days of classification
      - i. The notification should list appropriate steps for users to take, if any
      - ii. The notification must not include any details that could suggest an exploitation path
      - iii. The latter takes precedence over the former
    - b. MEDIUM and HIGH severities will require a Point Release
    - c. LOW severities will be addressed in the next Regular Release

8. Response Team applies appropriate patch(es)
    - a. Response Manager designates a PRIVATE git "hotfix branch" to work in
    - b. Patches are reviewed with the researcher
    - c. Any messages associated with PUBLIC commits during the time of review should not make reference to the security nature of the PRIVATE branch or its commits
    - d. Vulnerability announcement is drafted
      - i. Include severity of vulnerability
      - ii. Include systems/apps effected
      - iii. Include solutions (if any) if patch cannot be applied
    - e. Release date is discussed

9. At release date, Response Team coordinates with developers to finalize update:
    - a. Response Manager propagates the "hotfix branch" to trunk
    - b. Response Manager includes vulnerability announcement draft in release notes
    - c. Proceed with the Point or Regular Release

## IV. Post-release Disclosure Process

1. Response Team has 90 days to fulfill all points within section III

2. If the Incident Response process in section III is successfully completed:
    - a. Response Manager contacts researcher and asks if researcher wishes for credit
    - b. Finalize vulnerability announcement draft and include the following:
      - i. Project name and URL
      - ii. Versions known to be affected
      - iii. Versions known to be not affected (for example, the vulnerable code was introduced in a recent version, and older versions are therefore unaffected)
      - iv. Versions not checked
      - v. Type of vulnerability and its impact
      - vi. If already obtained or applicable, a CVE-ID
      - vii. The planned, coordinated release date
      - viii. Mitigating factors (for example, the vulnerability is only exposed in uncommon, non-default configurations)
      - ix. Workarounds (configuration changes users can make to reduce their exposure to the vulnerability)
      - x. If applicable, credits to the original reporter
    - c. Release finalized vulnerability announcement on website and reddit /r/Kovri
    - d. For HIGH severities, release finalized vulnerability announcement on well-known mailing lists:
      - i. oss-security@lists.openwall.com
      - ii. bugtraq@securityfocus.com
    - e. If applicable, developers request a CVE-ID
      - i. The commit that applied the fix is made reference too in a future commit and includes a CVE-ID

3. If the Incident Response process in section III is *not* successfully completed:
    - a. Response Team and developers organize an IRC meeting to discuss why/what points in section III were not resolved and how the team can resolve them in the future
    - b. Any developer meetings immediately following the incident should include points made in section V
    - c. If disputes arise about whether or when to disclose information about a vulnerability, the Response Team will publicly discuss the issue via IRC and attempt to reach consensus
    - d. If consensus on a timely disclosure is not met (no later than 90 days), the researcher (after 90 days) has every right to expose the vulnerability to the public

## V. Incident Analysis

1. Isolate codebase
    - a. Response Team and developers should coordinate to work on the following:
      - i. Problematic implementation of classes/libraries/functions, etc.
      - ii. Focus on apps/distro packaging, etc.
      - iii. Operator/config error, etc.

2. Auditing
    - a. Response Team and developers should coordinate to work on the following:
      - i. Auditing of problem area(s) as discussed in point 1
      - ii. Generate internal reports and store for future reference
      - iii. If results are not sensitive, share with the public via IRC or GitHub

3. Response Team has 45 days following completion of section III to ensure completion of section V

## VI. Resolutions

Any further questions or resolutions regarding the incident(s) between the researcher and response + development team after public disclosure can be addressed via the following:

- [GitHub](https://github.com/monero-project/kovri/issues/)
- [HackerOne](https://hackerone.com/monero)
- [Reddit /r/Kovri](https://reddit.com/r/Kovri/)
- IRC
- Email

## VII. Continuous Improvement

1. Response Team and developers should hold annual meetings to review the previous year's incidents

2. Response Team or designated person(s) should give a brief presentation, including:
    - a. Areas of Kovri affected by the incidents
    - b. Any network downtime or monetary cost (if any) of the incidents
    - c. Ways in which the incidents could have been avoided (if any)
    - d. How effective this process was in dealing with the incidents

3. After the presentation, Response Team and developers should discuss:
    - a. Potential changes to development processes to reduce future incidents
    - b. Potential changes to this process to improve future responses