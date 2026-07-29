---
title: Multiple Vulnerabilities in ELECOM Wireless LAN Routers and Access Points
date: 2026-07-28
categories: [SECURITY]
tags: [ELECOM,VULNERABILITIES,WIRELESS,LAN,SECURITY]
---

## Multiple Vulnerabilities in ELECOM Wireless LAN Routers and Access Points 🚨

Multiple wireless LAN routers and access points provided by **ELECOM CO.,LTD.** contain several vulnerabilities. Specifically, **CVE-2026-44387** and **CVE-2026-61376** affect:
- WAB-M1775-PS v2.1.9 and earlier
- WAB-S1775 v2.1.9 and earlier
- WAB-M2133 v2.0.5 and earlier
- WAB-I1750-PS v2.0.5 and earlier
- WAB-S1167-PS v2.0.5 and earlier.

Additionally, **CVE-2026-59764** impacts:
- WRC-X3000GS3-B v1.06 and earlier
- WRC-X3000GS3A-B v1.06 and earlier.

### Vulnerability Details 🔍
The vulnerabilities include reflected cross-site scripting (CWE-79), identified as **CVE-2026-44387**, with a **CVSS 4.0 Base Score** of 5.1 and **CVSS 3.0 Base Score** of 5.2. This vulnerability allows an arbitrary script to be executed on a logged-in user's web browser. 

Additionally, two OS command injection vulnerabilities (CWE-78) have been identified:
- **CVE-2026-59764**: An OS command injection in WebUI, with a **CVSS 4.0 Base Score** of 8.6 and **CVSS 3.0 Base Score** of 7.2.
- **CVE-2026-61376**: An OS command injection in Restore Settings, also with a **CVSS 4.0 Base Score** of 8.6 and **CVSS 3.0 Base Score** of 7.2.

For both **CVE-2026-59764** and **CVE-2026-61376**, an arbitrary OS command may be executed by an attacker who can log in to the product.

### Mitigation Steps 🛡️
To mitigate these risks, users must update the firmware. It is advised to update the firmware to the latest version according to the information provided by the developer.

### Reporting 📢
**CVE-2026-44387** was reported by **Kentaro Ishii** of GMO Cybersecurity by Ierae, Inc. to IPA, with **JPCERT/CC** coordinating with the developer. **Hirofumi Tanabe** of Mitsui Bussan Secure Directions, Inc. reported **CVE-2026-59764** to IPA, with **JPCERT/CC** also coordinating. **Rintaro Kawasugi** reported **CVE-2026-61376** to **ELECOM CO.,LTD.**, which subsequently reported the case to **JPCERT/CC** to notify users.

For more information, you can read the complete article here: [Read full article](https://jvn.jp/en/jp/JVN56870912/)