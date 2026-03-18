---
title: Vulnerabilities in Lantronix EDS3000PS and EDS5000
date: 2026-03-10
categories: [SECURITY]
tags: [LANTRONIX,VULNERABILITIES,SECURITY,ICS-CERT]
---

## Vulnerabilities in Lantronix EDS3000PS and EDS5000

**Date Published:** March 10, 2026

Successful exploitation of these vulnerabilities in **Lantronix EDS3000PS** and **EDS5000** could allow an attacker to bypass authentication and execute code with root-level privileges. These devices are deployed worldwide across Critical Infrastructure Sectors including Communications, Information Technology, and Critical Manufacturing. 🚀

### Affected Versions
- **EDS3000PS 3.1.0.0R2** (CVE-2025-67039, CVE-2025-70082, CVE-2025-67041)
- **EDS5000 2.1.0.0R3** (CVE-2025-67034, CVE-2025-67035, CVE-2025-67036, CVE-2025-67037, CVE-2025-67038)

### Details
For **EDS3000PS 3.1.0.0R2**, an issue (CVE-2025-67039) was discovered where authentication on management pages can be bypassed by appending a specific suffix to the URL and by sending an Authorization header that uses "admin" as the username. Additionally, the administrator password can be changed without knowledge of the current password (CVE-2025-70082). When chained with an authentication bypass vulnerability, this issue may allow unauthenticated attackers to modify the administrator password. Another issue (CVE-2025-67041) involves the host parameter of the TFTP client in the Filesystem Browser page not being properly sanitized, which can be exploited to escape from the original command and execute an arbitrary one with root privileges.

For **EDS5000 2.1.0.0R3**, multiple OS command injection vulnerabilities exist. For example, an authenticated attacker can inject OS commands into the "name" parameter when deleting SSL credentials (CVE-2025-67034). The SSH Client and SSH Server pages are also affected by multiple OS injection vulnerabilities due to missing sanitization of input parameters (CVE-2025-67035), allowing an attacker to inject arbitrary commands in delete actions of various objects, such as server keys, users, and known hosts. Commands are executed with root privileges. Another vulnerability (CVE-2025-67038) in the HTTP RPC module allows attackers to inject arbitrary OS commands into the username parameter during failed authentication attempts, which are executed with root privileges.

### Remediation
For remediations, Lantronix recommends users upgrade **EDS5000** to version **2.2.0.0R1** for vulnerabilities CVE-2025-67034 through CVE-2025-67038. For **EDS3000PS**, Lantronix recommends users upgrade to version **3.2.0.0R2** for CVE-2025-67039, CVE-2025-70082, and CVE-2025-67041. CISA recommends users take defensive measures to minimize the risk of exploitation of these vulnerabilities, such as minimizing network exposure for all control system devices and/or systems, ensuring they are not accessible from the Internet. CISA also recommends locating control system networks and remote devices behind firewalls and isolating them from business networks. When remote access is required, use more secure methods, such as Virtual Private Networks (VPNs). No known public exploitation specifically targeting these vulnerabilities has been reported to CISA at this time.

For more information, you can read the complete article here: [Read full article](https://www.cisa.gov/news-events/ics-advisories/icsa-26-069-02)