# OneKey Bug Bounty Program

This bug bounty program covers code within the OneKey repositories that directly impacts the security of OneKey products and users.

Please report bugs directly to [security@onekey.so](mailto:[security@onekey.so]) or submit through our official page on BugRap, where our pros have it covered.
// 改了邮箱为security@onekey.so

## Scope

| In Scope | Repository/URL |
|:---|:---|
| APP monorepo | [OneKey APP Monorepo](https://github.com/OneKeyHQ/app-monorepo) |
| Firmware | [OneKey Firmware](https://github.com/OneKeyHQ/firmware) |
| Hardware SDK | [OneKey Hardware SDK](https://github.com/OneKeyHQ/hardware-js-sdk) |
| Websites and Applications | *.onekey.so |

Submissions must target vulnerabilities present on the `master` branch (the main release branch).

<!-- Bounties for potential vulnerabilities include, but are not limited to:
- Private key handling, storage, and extraction / forensics
- CI/CD workflow and build pipeline vulnerabilities
- Domain hijacking and secrets compromise
- Authorization, authentication, and privilege escalation issues
// 来源：policy1_doc_security.md:L11-L16, policy3_repo_security.md:L9-L14 -->

If a vulnerability resides in the repository and materially affects OneKey's security posture, it may be eligible for a bounty.
// 来源：policy1_doc_security.md:L18, policy3_repo_security.md:L15

<!-- ## Prioritized Focus Areas
// 来源：policy3_repo_security.md:L19

- Reports demonstrating how an attacker could extract the secret recovery phrase, private key, or mnemonic from a wallet or device.
- Reports demonstrating how an attacker could make a user's wallet behave in unexpected ways (e.g., signing unintended transactions, displaying incorrect information on confirmation screens).
- Reports demonstrating supply chain attacks or firmware-level compromises.
// 来源：policy3_repo_security.md:L21-L23 -->

## Rules & Guidelines
// 来源：policy1_doc_security.md:L22, policy3_repo_security.md:L25

### Responsible Disclosure Policy
// 来源：policy1_doc_security.md:L24

Participants must adhere to responsible disclosure practices. **You must not:**
- Publicly disclose a vulnerability before OneKey has confirmed remediation or provided explicit written authorization.
- Exploit a vulnerability beyond the minimum necessary to demonstrate proof of concept.
- Access, modify, or delete data belonging to other users.
- Perform any testing against production systems that could degrade service availability or user experience.
- Engage in social engineering, phishing, or physical attacks against OneKey employees, users, or infrastructure.
- Use a scanner for large-scale scanning. (If the business system or network becomes unavailable due to scanning, it will be handled according to relevant laws.)
- Conduct destructive testing. Vulnerability testing is strictly limited to PoC (proof of concept). If harms are caused inadvertently during testing, report it immediately and detail any sensitive operations (e.g., deletion, modification) performed during the test.
- Use excessively aggressive payloads if preventable. When testing XSS, avoid modifying the page directly, continuously popping up message boxes (log is recommended for XSS verification), or stealing Cookies/user information (for blind XSS testing, please use DNSLog). If an aggressive payload was accidentally used, please delete it in time.

Violation of these rules will result in immediate disqualification from the program and forfeiture of any pending bounties. OneKey reserves the right to pursue legal remedies for violations that cause harm.

### Submission Guidelines & Reporting Rules

All vulnerability reports must be submitted through one of the following channels:
1. **Private disclosure**: Send an email to [security@onekey.so](mailto:[security@onekey.so]) — recommended for high-severity vulnerabilities. Private submissions remain fully eligible for bounties.
2. **BugRap Platform**: Submit through our official page on [BugRap](https://bugrap.io/bounties/OneKey).

All submissions must follow the format defined in the issue template. Reports must include:
- A clear description of the vulnerability
- Step-by-step reproduction instructions, which may include screenshots, videos, scripts, etc.
- A working proof of concept (where applicable)
- An assessment of impact and affected components

Clarity, thoroughness, and quality of documentation will be considered when determining reward amount. For high-severity vulnerabilities (P0/P1), we strongly recommend private disclosure. Public disclosure of critical vulnerabilities without prior coordination may affect eligibility and reward amount. All reports must be accompanied with a working proof-of-concept or clear reproduction steps that demonstrates the impact described by the submission. Reports which claim to have a specified impact that is later proven false (and does not result in action from the OneKey security team) may be closed as Not-Applicable. Reports which do not meet our severity threshold for a bounty, but still result in meaningful action amongst our security team, will be closed as resolved when the ticket is added to our backlog.
// 来源：policy1_doc_security.md:L50-L52, policy3_repo_security.md:L27-L31

### Multiple Reports (Duplicate and Overlapping Reports)
// 来源：policy1_doc_security.md:L93, policy2_bug_rap_policy.md:L19

In case of multiple reports about the same issue, OneKey will reward the earliest valid and actionable submission (First-Actionable). This means we prioritize the report that first provides adequate details allowing our team to reproduce and confirm the vulnerability.
// 来源：policy1_doc_security.md:L95-L96, policy2_bug_rap_policy.md:L19, policy3_repo_security.md:L87-L89

Only the **first valid report** of a given vulnerability is eligible for a bounty. Reports describing the same root cause across different attack vectors or multiple vulnerabilities caused by one underlying issue will be awarded one/single bounty.
// 来源：policy1_doc_security.md:L95, policy1_doc_security.md:L98, policy3_repo_security.md:L151

OneKey may, at its discretion, award partial bounties for duplicate reports that contribute materially new information.
// 来源：policy1_doc_security.md:L97

## Evaluation and Severity
// 来源：policy1_doc_security.md:L58, policy3_repo_security.md:L34

Submissions will be evaluated by the OneKey security team using multiple criteria. It is at the sole discretion of OneKey to determine whether a report qualifies as a valid vulnerability, the severity classification, the bounty amount awarded, and whether derivative reports are eligible. All decisions by OneKey are final.
// 来源：policy1_doc_security.md:L62-L69, policy3_repo_security.md:L38

### Rating Standards
// 来源：User Request

We utilize the following standards to assist in evaluating vulnerabilities:
1. **OWASP Risk Rating Methodology**: Considers both **Impact** and **Likelihood**.
// 来源：policy1_doc_security.md:L60, policy3_repo_security.md:L36
2. **CVSS 3.1 Standards**: Will be used for standard vulnerability rating ([CVSS3.1](https://nvd.nist.gov/vuln-metrics/cvss/v3-calculator)).
// 来源：policy2_bug_rap_policy.md:L21

3. **OneKey CVSS Scoring Guide**: Tailored specifically to our hardware wallet and software ecosystem to maintain consistency and transparency.
// 来源：policy3_repo_security.md:L58-L60

| Metric | Options |
|--------|---------|
| **Attack Vector (AV)** | **Network (N):** The attack can be executed over a network connection.<br>**Physical (P):** The attack requires physical access to the hardware wallet device.<br>**Local (L):** The attack requires local execution by malicious software/user on the host machine. |
| **Attack Complexity (AC)** | **High (H):** A successful exploit requires overcoming specific conditions beyond the attacker's control.<br>**Low (L):** No specialized access conditions exist. The attack can be reliably executed. |
| **Scope (S)** | **Changed (C):** The vulnerability impacts resources beyond capabilities provided by its authorizing scope.<br>**Unchanged (U):** The vulnerability only impacts resources within its authorized scope. |
| **Privileges Required (PR)** | **High (H):** Requires elevated access (e.g., paired Bluetooth device, USB debug access).<br>**Low (L):** Requires the webpage/dApp to be connected to the wallet.<br>**None (N):** Exploit without prior connection or privilege. |
| **User Interaction (UI)** | **Required (R):** Exploitation requires some user interaction.<br>**None (N):** Exploitation does not require user interaction. |
| **Confidentiality Impact (C)**| **High (H):** Disclosure of a cryptographic element in custody.<br>**Low (L):** Disclosure of non-critical user information. |
| **Integrity Impact (I)** | **High (H):** A cryptographic asset or key security control loses its integrity.<br>**Low (L):** A non-critical user interface element loses its integrity. |
| **Availability Impact (A)** | **High (H):** Awarded selectively on a case-by-case basis.<br>**Low (L):** Application/device becomes unusable but recoverable via reinstall/reset. |
// 来源：policy3_repo_security.md:L62-L81

*(Note: As this guide evolves, changes will only apply to new reports. The OneKey team will not make adjustments retroactively to past bounties.)*
// 来源：policy3_repo_security.md:L83

## Bounty Amounts
// 来源：policy1_doc_security.md:L71, policy2_bug_rap_policy.md:L15

Rewards will be provided according to the rules of this bug bounty program. At the discretion of OneKey, quality, creativity, or novelty of submissions may modify payouts within a given range.
// 来源：policy2_bug_rap_policy.md:L17

Severity levels are based on:
- **Severity & Impact**: The potential impact of the vulnerability if exploited. Higher severity will be awarded to vulnerabilities that could result in loss of funds, compromise of private keys, or an irrecoverable state.
- **Likelihood**: The probability that the vulnerability will affect users.
- **Report quality**: Clarity of description, completeness of reproduction steps, and quality of proof of concept.
- **Researcher conduct**: Whether the researcher adhered to responsible disclosure practices and avoided destructive actions.
- **Originality**: Whether the researcher independently discovered the vulnerability (reports from public info may receive reduced bounds).
// 来源：policy1_doc_security.md:L81-L89, policy3_repo_security.md:L48-L56

**Note: All reward amounts below are specified in USD, but use the specific target categorizations.**
// 来源：User Request

### 1. APP Monorepo (iOS/Android/MacOS/Linux/Windows/Chrome Extension)
// 来源：policy2_bug_rap_policy.md:L24
| Severity | Description | Reward (USD) |
|:---:|:---|:---:|
| Critical (P0) | Critical severity vulnerabilities will have a significant impact on the security of the project, and it is strongly recommended to fix the critical vulnerabilities. | $5,000 ~ $10,000 |
| High (P1) | High severity vulnerabilities will affect the normal operation of the project. It is strongly recommended to fix high-risk vulnerabilities. | $2,000 ~ $5,000 |
| Medium (P2) | Medium severity vulnerability will affect the operation of the project. It is recommended to fix medium-risk vulnerabilities. | $500 ~ $1,000 |
| Low (P3) | Low severity vulnerabilities may affect the operation of the project in certain scenarios. It is suggested that the project team evaluate whether to fix them. | $250 ~ $500 |
// 来源：policy2_bug_rap_policy.md:L26-L31

### 2. Firmware
// 来源：policy2_bug_rap_policy.md:L35
| Severity | Description | Reward (USD) |
|:---:|:---|:---:|
| Critical (P0) | Critical severity vulnerabilities will have a significant impact on the security of the project, and it is strongly recommended to fix the critical vulnerabilities. | $6,000 ~ $10,000 |
| High (P1) | High severity vulnerabilities will affect the normal operation of the project. It is strongly recommended to fix high-risk vulnerabilities. | $3,000 ~ $6,000 |
| Medium (P2) | Medium severity vulnerability will affect the operation of the project. It is recommended to fix medium-risk vulnerabilities. | $1,000 ~ $1,500 |
| Low (P3) | Low severity vulnerabilities may affect the operation of the project in certain scenarios. It is suggested that the project team evaluate whether to fix them. | $500 ~ $1,000 |
// 来源：policy2_bug_rap_policy.md:L38-L43

### 3. Hardware JS SDK
// 来源：policy2_bug_rap_policy.md:L46
| Severity | Description | Reward (USD) |
|:---:|:---|:---:|
| Critical (P0) | Critical severity vulnerabilities will have a significant impact on the security of the project, and it is strongly recommended to fix the critical vulnerabilities. | $2,000 ~ $4,000 |
| High (P1) | High severity vulnerabilities will affect the normal operation of the project. It is strongly recommended to fix high-risk vulnerabilities. | $1,400 ~ $2,000 |
| Medium (P2) | Medium severity vulnerability will affect the operation of the project. It is recommended to fix medium-risk vulnerabilities. | $300 ~ $700 |
| Low (P3) | Low severity vulnerabilities may affect the operation of the project in certain scenarios. It is suggested that the project team evaluate whether to fix them. | $50 ~ $300 |
// 来源：policy2_bug_rap_policy.md:L48-L53

### 4. Websites and Applications
// 来源：policy2_bug_rap_policy.md:L55
| Severity | Description | Reward (USD) |
|:---:|:---|:---:|
| Critical (P0) | Critical severity vulnerabilities will have a significant impact on the security of the project, and it is strongly recommended to fix the critical vulnerabilities. | $2,000 ~ $4,000 |
| High (P1) | High severity vulnerabilities will affect the normal operation of the project. It is strongly recommended to fix high-risk vulnerabilities. | $1,400 ~ $2,000 |
| Medium (P2) | Medium severity vulnerability will affect the operation of the project. It is recommended to fix medium-risk vulnerabilities. | $300 ~ $700 |
| Low (P3) | Low severity vulnerabilities may affect the operation of the project in certain scenarios. It is suggested that the project team evaluate whether to fix them. | $50 ~ $300 |
// 来源：policy2_bug_rap_policy.md:L57-L62

*(OneKey reserves the right to adjust bounty amounts at any time without prior notice. Bounty amounts listed represent maximum values per tier, not guaranteed payouts.)*
// 来源：policy1_doc_security.md:L91

## Response Targets
// 来源：policy3_repo_security.md:L91

OneKey will make a best effort to meet the following SLAs for researchers participating in our program:
| Type of Response | SLA in Business Days |
|---|---|
| First Response | 2 days |
| Time to Triage | 5 days |
| Time to Bounty | 14 days |
| Time to Resolution | Depends on severity & complexity |
// 来源：policy3_repo_security.md:L93-L100

## Out of Scope / Ineligible Submissions
// 来源：policy1_doc_security.md:L102, policy2_bug_rap_policy.md:L65, policy3_repo_security.md:L110

Any vulnerabilities or flaws in other software tools created by OneKey (e.g., OneKeyJS, purser, tailor, etc.) are not eligible. Flaws in these software tools are welcome disclosures but will not be awarded bounties for this bug bounty program.
// 来源：policy1_doc_security.md:L104-L105, policy2_bug_rap_policy.md:L67, policy3_repo_security.md:L112

When reporting vulnerabilities, please consider (1) attack scenario / exploitability, and (2) security impact of the bug. The following issues are considered **out of scope**:
// 来源：policy1_doc_security.md:L103, policy3_repo_security.md:L114

**Attack Vectors & Exploits:**
- Attacks and vulnerabilities that depend on compromised keys or other security flaws outside the OneKey codebase (keyloggers, intercepted communications, social engineering exploits, etc.).
- Attacks requiring a compromised victim device, including attacks requiring the user to install a malicious application, execute malicious scripts, disable device security settings, or jailbreak/root their device.
- Attacks requiring MITM or physical access to a user's device (note: physical attacks on the hardware wallet device itself may still be in scope if they demonstrate a novel hardware vulnerability).
- Vulnerabilities whose exploit chain fundamentally relies on leveraging an external 0-day, 1-day, or n-day vulnerability (i.e., in systems not developed/controlled by OneKey, operating systems, frameworks, dependency libraries, hardware chips, etc.). OneKey reserves the right to reduce the bounty or invalidate such reports.
- Secret Recovery Phrase / Mnemonic brute-forcing. Reports attempting to brute force seed phrases are not valid or eligible. (Does not apply to legitimate cryptographic weaknesses in seed phrase generation).
- Exploits requiring seed phrase entry. Users are consistently reminded to never provide their seed phrase. Reports requiring users to act outside these guidelines are out of scope.
// 来源：policy1_doc_security.md:L108, L113, L114, L123, policy2_bug_rap_policy.md:L68, L73, L74, L81, policy3_repo_security.md:L116-L118, L122, L141

**System Design & Business Logic:**
- Attacks that are accounted for in the system design (e.g., Ethereum network spamming, malicious reputation mining/gaming, administrative malfeasance).
- Critiques of the OneKey and overall mechanism design. We welcome suggestions and constructive criticism directed to dev@onekey.so.
- Any activity that could lead to the disruption of our service availability (DoS/DDoS).
- Issues that require unlikely or impractical user interaction.
- Perceived security weaknesses without evidence of the ability to demonstrate impact (e.g., missing best practices, functional bugs without security implications, recommended security improvements).
// 来源：policy1_doc_security.md:L109-L110, L117, L126, L127, policy2_bug_rap_policy.md:L69-L70, L77, L86, L87, policy3_repo_security.md:L119-L120, L128, L133, L140

**Application & Web Vulnerabilities:**
- Clickjacking on pages with no sensitive actions.
- Cross-Site Request Forgery (CSRF) on unauthenticated forms or forms with no sensitive actions.
- Comma Separated Values (CSV) injection without demonstrating a vulnerability/attack vector.
- Content spoofing and text injection issues without showing an attack vector / without being able to modify HTML/CSS.
- Rate limiting or brute force issues on non-authentication endpoints.
- Software version disclosure / Banner identification issues / Descriptive error messages or headers (e.g., stack traces, application or server errors).
- Tabnabbing.
- Open redirect — unless an additional security impact can be demonstrated.
- Previously known vulnerable libraries without a working Proof of Concept demonstrating exploitability.
// 来源：policy1_doc_security.md:L111-L112, L115-L116, L118-L119, L121, L124-L125, policy2_bug_rap_policy.md:L71-L72, L75-L76, L78-L79, L82, L84-L85, policy3_repo_security.md:L129-L132, L134-L136, L138-L139

**Third-party, Infrastructure & Other Elements:**
- Vulnerabilities that involve external libraries, third-party dependencies, or submodules not authored by the OneKey team will be evaluated on a case-by-case basis. Eligibility and reward amount for such reports are at OneKey's sole discretion.
- Vulnerabilities only affecting users of outdated or unpatched browsers (less than 2 stable versions behind the latest released stable version).
- Public zero-day vulnerabilities that have had an official patch for less than 1 month will be awarded on a case-by-case basis.
- Reporting a leaked token or credential without validation. Reporters must validate that leaked tokens from our applications are valid and can access sensitive operations. User API keys or SRPs leaked online are not valid reports.
- Malicious RPC servers. Reports requiring malicious RPCs remain out of scope unless the RPC can impact resources beyond its expected scope (e.g., achieving XSS, tampering with restricted state). Misleading data such as faking balances or transactions remains out of scope.
- Mobile browser issues without security or privacy impact, or mobile browser resource exhaustion / DoS that user can recover from through standard actions.
- Third-party plugin or extension vulnerabilities. Report third-party plugin or extension vulnerabilities to the respective developer first.
- Vulnerabilities already known to the OneKey team or currently being remediated.
- Vulnerabilities discovered through automated scanning tools without manual verification and a clear proof of concept.
// 来源：policy1_doc_security.md:L20, L120, L122, L128-L129, policy2_bug_rap_policy.md:L80, L83, policy3_repo_security.md:L17, L121, L123-L127

## Legal Safe Harbor
// 来源：policy1_doc_security.md:L131

OneKey will not pursue legal action against researchers who:
- Act in good faith and comply with this program's rules
- Avoid privacy violations, data destruction, and service disruption
- Report vulnerabilities through the designated channels
- Do not publicly disclose vulnerabilities prior to OneKey's confirmation of remediation

This safe harbor does not extend to activities that violate applicable law or that cause harm to OneKey, its users, or third parties.
// 来源：policy1_doc_security.md:L133-L140

## Funding Your Wallet
// 来源：policy3_repo_security.md:L143

To experiment with OneKey without using your own ETH, switch your default network to Sepolia test network and use a faucet such as [Infura Faucet](https://www.infura.io/faucet) to get test funds.
// 来源：policy3_repo_security.md:L145

## Program Terms
// 来源：policy1_doc_security.md:L142

- OneKey reserves the right to modify, suspend, or terminate this bug bounty program at any time without prior notice.
- Participation in this program does not create an employment, contractor, or agency relationship with OneKey.
- Bounties are paid at OneKey's discretion and are subject to applicable tax obligations of the recipient.
- By submitting a report, the researcher grants OneKey an unrestricted, perpetual license to use the report and any associated materials for the purpose of improving OneKey's security.
- OneKey may publicly acknowledge researchers (with their consent) but is not obligated to provide public credit.
- All disputes arising from this program will be governed by the laws of the jurisdiction in which OneKey is incorporated.
// 来源：policy1_doc_security.md:L144-L149
