### Project Overview

OneKey hardware wallet is a 100% open-source hardware wallet that supports over 1,000 cryptocurrencies including Bitcoin, Ethereum, USDT, USDC, BCH, XRP, Tron, Doge, LTC, Dash, Aptos, Sui, Cosmos, Polkadot, and Kusama.

### Scopes

| 	In Scope     |                                                   |
|:----------------:| ------------------------------------------------- |
|APP monorepo|[OneKey APP Monorepo](https://github.com/OneKeyHQ/app-monorepo)|
|Firmware|[OneKey Firmware](https://github.com/OneKeyHQ/firmware)|
|Hardware SDK|[OneKey Hardware SDK](https://github.com/OneKeyHQ/hardware-js-sdk)|
|Websites and Applications|            *.onekey.so                  |        


### Rewards

Rewards will be provided according to the rules of this bug bounty program as outlined above. At the discretion of OneKey, quality, creativity, or novelty of submissions may modify payouts within a given range.

In case of multiple reports about the same issue, OneKey will reward the earliest submission, regardless of how the issue was reported.

CVSS standards will be used for vulnerability rating([CVSS3.1](https://nvd.nist.gov/vuln-metrics/cvss/v3-calculator)).


#### 1.APP Monorepo(both iOS/android/MacOS/Linux/Windows/Chrome Extension)

|   Severity    |   Description    |    Reward   |
|:-------------:| ---------------- |:-----------:|
| Critical |Critical severity vulnerabilities will have a significant impact on the security of the project, and it is strongly recommended to fix the critical vulnerabilities.|5,000 ~ 10,000 USDC|
|  High  |High severity vulnerabilities will affect the normal operation of the project. It is strongly recommended to fix high-risk vulnerabilities.|2,000 ~ 5,000 USDC|
| Medium |Medium severity vulnerability will affect the operation of the project. It is recommended to fix medium-risk vulnerabilities.|500 ~ 1,000 USDC|
|  Low  |Low severity vulnerabilities may affect the operation of the project in certain scenarios. It is suggested that the project team should evaluate and consider whether these vulnerabilities need to be fixed.|250 ~ 500 USDC|



#### 2.Firmware


|   Severity    |   Description    |    Reward   |
|:-------------:| ---------------- |:-----------:|
| Critical |Critical severity vulnerabilities will have a significant impact on the security of the project, and it is strongly recommended to fix the critical vulnerabilities.|6,000 ~ 10,000 USDC|
|  High  |High severity vulnerabilities will affect the normal operation of the project. It is strongly recommended to fix high-risk vulnerabilities.|3,000 ~ 6,000 USDC|
|  Medium  |Medium severity vulnerability will affect the operation of the project. It is recommended to fix medium-risk vulnerabilities.|1,000 ~ 1,500 USDC|
|  Low  |Low severity vulnerabilities may affect the operation of the project in certain scenarios. It is suggested that the project team should evaluate and consider whether these vulnerabilities need to be fixed.|500 ~ 1,000 USDC|


#### 3.Hardware JS SDK

|   Severity    |   Description    |    Reward   |
|:-------------:| ---------------- |:-----------:|
| Critical |Critical severity vulnerabilities will have a significant impact on the security of the project, and it is strongly recommended to fix the critical vulnerabilities.|2,000 ~ 4,000 USDC|
|  High  |High severity vulnerabilities will affect the normal operation of the project. It is strongly recommended to fix high-risk vulnerabilities.|1400 ~ 2,000 USDC|
|  Medium  |Medium severity vulnerability will affect the operation of the project. It is recommended to fix medium-risk vulnerabilities.|300 ~ 700 USDC|
|  Low  |Low severity vulnerabilities may affect the operation of the project in certain scenarios. It is suggested that the project team should evaluate and consider whether these vulnerabilities need to be fixed.|50 ~ 300 USDC|

#### 4.Websites and Applications

|   Severity    |   Description    |    Reward   |
|:-------------:| ---------------- |:-----------:|
| Critical |Critical severity vulnerabilities will have a significant impact on the security of the project, and it is strongly recommended to fix the critical vulnerabilities.|2,000 ~ 4,000 USDC|
|  High  |High severity vulnerabilities will affect the normal operation of the project. It is strongly recommended to fix high-risk vulnerabilities.|1400 ~ 2,000 USDC|
|  Medium  |Medium severity vulnerability will affect the operation of the project. It is recommended to fix medium-risk vulnerabilities.|300 ~ 700 USDC|
|  Low  |Low severity vulnerabilities may affect the operation of the project in certain scenarios. It is suggested that the project team should evaluate and consider whether these vulnerabilities need to be fixed.|50 ~ 300 USDC|


### Out of Scopes

Any vulnerabilities or flaws in other software tools created by OneKey (e.g. OneKeyJS, purser, tailor, etc.) are not eligible. The following issues are considered out of scope:
- Attacks and vulnerabilities that depend on compromised keys or other security flaws outside the OneKey codebase (keyloggers, intercepted communications, social engineering exploits, etc.).
- Attacks that are accounted for in the system design, i.e. Ethereum network spamming, malicious reputation mining, malfeasance in OneKey administration.
- Critiques of the OneKey and overall mechanism design. We welcome suggestions and constructive criticism, and ask that it be directed to [dev@OneKey.so](dev@OneKey.so) .
- Clickjacking on pages with no sensitive actions
- Cross-Site Request Forgery (CSRF) on unauthenticated forms or forms with no sensitive actions
- Attacks requiring MITM or physical access to a user's device.
- Attacks requiring a compromised victim device.
- Previously known vulnerable libraries without a working Proof of Concept.
- Comma Separated Values (CSV) injection without demonstrating a vulnerability.
- Any activity that could lead to the disruption of our service (DoS).
- Content spoofing and text injection issues without showing an attack vector/without being able to modify HTML/CSS
- Rate limiting or bruteforce issues on non-authentication endpoints
- Vulnerabilities only affecting users of outdated or unpatched browsers [Less than 2 stable versions behind the latest released stable version]
- Vulnerability reports where the exploit chain fundamentally relies on leveraging an external 0-day, 1-day, or n-day vulnerability (i.e., vulnerabilities in systems or components not developed or controlled by OneKey, including but not limited to operating systems, development frameworks, dependency libraries, hardware chips, etc.). In such cases, OneKey reserves the right to reduce the bug bounty reward or invalidate the report.
- Software version disclosure / Banner identification issues / Descriptive error messages or headers (e.g. stack traces, application or server errors).
- Public Zero-day vulnerabilities that have had an official patch for less than 1 month will be awarded on a case by case basis.
- Tabnabbing
- Open redirect - unless an additional security impact can be demonstrated
- Issues that require unlikely user interaction
- Perceived security weaknesses without evidence of the ability to demonstrate impact (e.g. Missing best practices, functional bugs without security implications, etc.)

### Reporting rules

- Rewards or recognition require that the OneKey security team can reproduce and verify an issue and that the security impact is clear;
- Reproduction steps need to be clear, and may include screenshots, videos, scripts, etc;
- Do not conduct social engineering and phishing to people;
- Do not leak the details of the vulnerability;
- Do not use a scanner for large-scale scanning. If the business system or network becomes unavailable, it will be handled according to relevant laws;
- Those who test the vulnerability should try to avoid modifying the page directly, continuing popping up the message box (log is recommended for XSS verification), stealing Cookies, and obtaining aggressive payload such as the user information (for blind XSS testing, please use DNSLog). If you accidentally used a more aggressive payload, please delete it in time; 
- Vulnerability testing is only limited to PoC(proof of concept), and destructive testing is strictly prohibited. If harms are caused inadvertently during the testing, it should be reported in time. Meanwhile, sensitive operations performed in the test, such as deletion, modification, and other operations, are required to be explained in the report.ch as deletion, modification, and other operations, are required to be explained in the report.