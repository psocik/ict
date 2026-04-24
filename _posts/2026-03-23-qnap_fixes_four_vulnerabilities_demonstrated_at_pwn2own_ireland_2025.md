---
title: QNAP Fixes Four Vulnerabilities Demonstrated at Pwn2Own Ireland 2025
date: 2026-03-23
categories: [SECURITY]
tags: [QNAP,VULNERABILITIES,PWN2OWN,SECURITY]
---

## QNAP Fixes Four Vulnerabilities Demonstrated at Pwn2Own Ireland 2025

🚀 QNAP has successfully addressed four vulnerabilities showcased at Pwn2Own 2025 that could potentially allow code execution, data access, or system disruption. The Taiwanese vendor has patched multiple vulnerabilities, including four SD-WAN router issues (CVE-2025-62843 to CVE-2025-62846) demonstrated by Team DDOS during the event. The team managed to chain several bugs in QNAP devices to gain root access, earning a reward of $100,000! 💰

### Details of the Vulnerabilities
- **CVE-2025-62843**: This issue involves communication channel restrictions. If an attacker gains physical access to the device, they can exploit this flaw to obtain privileges intended for other endpoints, effectively bypassing existing controls.
- **CVE-2025-62844**: This vulnerability affects the local network level. An attacker with LAN access can exploit weak authentication mechanisms to retrieve sensitive information, exposing data that should remain protected.
- **CVE-2025-62846**: This critical vulnerability comes into play when an attacker gains administrative credentials. By exploiting an SQL injection vulnerability, they can execute unauthorized commands, compromising the integrity and control of the system.
- **CVE-2025-62845**: This relates to improper handling of escape and control sequences. An attacker with elevated privileges can trigger unexpected system behavior, potentially impacting stability and security.

Overall, these vulnerabilities highlight how a combination of physical access, network exposure, and elevated privileges can amplify risk. Timely patching and strong security practices are essential! 🔒

Additionally, in November 2025, QNAP patched seven zero-day vulnerabilities exploited at Pwn2Own Ireland 2025, affecting various systems including QTS, QuTS hero, and more.

For further details, check out the full article: [Read full article](https://securityaffairs.com/189871/security/qnap-fixed-four-vulnerabilities-demonstrated-at-pwn2own-ireland-2025.html)