---
title: Multiple Vulnerabilities in Image Scanner Driver for Linux
date: 2026-09-29
categories: [SECURITY]
tags: [VULNERABILITIES,LINUX,IMAGE-SCANNER,SECURITY]
---

## Multiple Vulnerabilities in Image Scanner Driver for Linux 🚨

The Image Scanner Driver for Linux, provided by PFU Limited, contains multiple vulnerabilities that could affect your system. These vulnerabilities impact the following versions:
- **fi Series**: V2.0.0, V2.1.0, V2.1.1, V2.3.2, V2.5.0, V2.7.0, V2.7.1, V2.8.0, V2.8.1, V2.8.2
- **SP Series**: V2.0.0, V2.1.0, V2.1.1, V2.1.1-4, V2.2.0, V2.2.1, V2.2.2, V2.3.0

### Identified Vulnerabilities 🔍

1. **OS Command Injection Vulnerability (CWE-78)**
   - **CVE-2026-78229**
   - **CVSS Base Score**: 5.4 (CVSS:4.0), 6.7 (CVSS:3.1)
   - An attacker with access to a Linux system where the affected product is installed may execute arbitrary OS commands.

2. **Link Following Vulnerability (CWE-59)**
   - **CVE-2026-81310**
   - **CVSS Base Score**: 5.2 (CVSS:4.0), 6.6 (CVSS:3.1)
   - An attacker may overwrite arbitrary files by using a special method in advance.

### Recommended Actions ✅

To mitigate these vulnerabilities, users should update the software to the latest version as advised by the developer. Nir Yehoshua of Cipher Security Labs reported these vulnerabilities to PFU Limited, which coordinated the response and notified JPCERT/CC to inform users of the solution.

For further details, you can read the complete article here: [Read full article](https://jvn.jp/en/vu/JVNVU96968110/) 

Stay safe and keep your systems updated! 💻