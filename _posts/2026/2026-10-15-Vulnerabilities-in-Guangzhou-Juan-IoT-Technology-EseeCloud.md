---
title: Vulnerabilities in Guangzhou Juan IoT Technology EseeCloud
date: 2026-10-15
categories: [TECHNOLOGY]
tags: [VULNERABILITIES,IOT,SECURITY,CISA]
---

## Vulnerabilities in Guangzhou Juan IoT Technology EseeCloud

🚨 **Attention**: Successful exploitation of these vulnerabilities could allow an attacker to gain control over affected IP cameras. The following versions of Guangzhou Juan IoT Technology EseeCloud are affected: EseeCloud App <=4.9.6 and EseeCloud Firmware <=4.9.86.0.

### Identified Vulnerabilities

- **CVE-2026-107617**: Involves a hard-coded credential (CWE-798). An attacker can use this hard-coded credential to log in to EseeCloud devices.
- **CVE-2026-97858**: Classified as an Improperly Controlled Modification of Dynamically-Determined Object Attributes (CWE-915). This allows an attacker to cause the server to unbind the target device from its current owner and rebind it to the requesting account.
- **CVE-2026-105664**: An Observable Response Discrepancy (CWE-204) that exposes an observable response discrepancy when processing ID values.

### Recommendations

CISA recommends users take defensive measures to minimize the risk of exploitation of these vulnerabilities:
- Minimize network exposure for all control system devices and/or systems.
- Ensure they are not accessible from the internet.
- Locate control system networks and remote devices behind firewalls and isolate them from business networks.
- When remote access is required, use more secure methods, such as virtual private networks (VPNs).

No known public exploitation specifically targeting these vulnerabilities has been reported to CISA at this time. For all identified vulnerabilities, Guangzhou Juan IoT Technology Co., Ltd. did not respond to CISA's coordination attempts. EseeCloud users are advised to contact Guangzhou Juan IoT Technology Co., Ltd. for support.

For more details, please visit the [CISA advisory](https://www.cisa.gov/news-events/ics-advisories/icsa-26-288-02).