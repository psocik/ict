---
title: Multiple Vulnerabilities Found in ELECOM Wireless LAN Products
date: 2026-02-03
categories: [SECURITY]
tags: [ELECOM,WIRELESS,VULNERABILITIES,SECURITY]
---

## Multiple Vulnerabilities in ELECOM Wireless LAN Products 🚨

Wireless LAN products provided by **ELECOM CO.,LTD.** contain multiple vulnerabilities that could potentially compromise user security. Here’s a breakdown of the vulnerabilities:

- **Cross-site request forgery (CWE-352)** (CVE-2026-20704) with CVSS 4.0 Base Score 5.1 and CVSS 3.0 Base Score 4.3.
- **OS command injection (CWE-78)** (CVE-2026-22550) has CVSS 4.0 Base Score 8.6 and CVSS 3.0 Base Score 7.2.
- **Use of weak credentials (CWE-1391)** (CVE-2026-24449) has CVSS 4.0 Base Score 5.1 and CVSS 3.0 Base Score 4.6.
- **Stack-based buffer overflow (CWE-121)** (CVE-2026-24465) has CVSS 4.0 Base Score 9.3 and CVSS 3.0 Base Score 9.8.

### Affected Models 📦
- CVE-2026-20704 and CVE-2026-22550 affect **WRC-X1500GS-B v1.12** and earlier versions, and **WRC-X1500GSA-B v1.12** and earlier versions.
- CVE-2026-24449 affects **WRC-X1500GS-B** all versions, and **WRC-X1500GSA-B** all versions.
- CVE-2026-24465 affects **WAB-S733IW2-PD v5.5.00** and earlier versions, **WAB-S733IW-AC v5.5.00** and earlier versions, **WAB-S733IW-PD** all versions, **WAB-S300IW2-PD v5.5.00** and earlier versions, **WAB-S300IW-AC v5.5.00** and earlier versions, and **WAB-S300IW-PD** all versions.

### Impact ⚠️
If a user accesses a malicious page while logged in to the affected product, unintended operations may occur due to CVE-2026-20704. An arbitrary OS command may be executed by a logged-in user through CVE-2026-22550. The initial passwords can be easily calculated from the system information because of CVE-2026-24449. A crafted packet may lead to arbitrary code execution via CVE-2026-24465.

### Recommended Actions 🔧
To address these vulnerabilities, users should:
- Update and configure the firmware properly.
- Stop using unsupported products like **WAB-S733IW-PD** and **WAB-S300IW-PD**.
- Change the passwords for the admin page and Wi-Fi connection to strong, hard-to-guess ones after updating the firmware.

These vulnerabilities were reported by several researchers. For more details, read the complete article [here](https://jvn.jp/en/jp/JVN94012927/).