---
title: Multiple Vulnerabilities Found in Cybozu Garoon
date: 2026-02-02
categories: [SECURITY]
tags: [CYBOZU,VULNERABILITIES,SECURITY,CVE]
---

## Multiple Vulnerabilities in Cybozu Garoon 🚨

Multiple vulnerabilities have been identified in **Cybozu Garoon**, detailed in JVN#35265756 and published on **February 2, 2026**. The affected products include Cybozu Garoon versions **5.0.0 to 6.0.3** and **5.15.0 to 6.0.3**.

### Vulnerabilities Overview:
- **Cross-Site Scripting Vulnerability in E-mail** (CWE-79)
  - **CVE-2026-20711** (CyVDB-3687)
  - CVSS:4.0 base score of **6.9**

- **Cross-Site Scripting Vulnerability in Message** (CWE-79)
  - **CVE-2026-22881** (CyVDB-3689)
  - CVSS:4.0 base score of **6.8**

- **Improper Input Verification in Portal Setting** (CWE-231)
  - **CVE-2026-22888** (CyVDB-3995)
  - CVSS:4.0 base score of **6.9**

### Impact:
An attacker could exploit these vulnerabilities to reset arbitrary users’ passwords or alter data related to portal settings, potentially blocking access to the product.

### Recommended Action:
To mitigate these vulnerabilities, it is crucial to update the software to the latest version as advised by the developer.

### Acknowledgments:
- **Masato Kinugawa** reported CVE-2026-20711 to Cybozu, Inc., which was then communicated to JPCERT/CC for user notification.

For more details, read the complete article here: [Read full article](https://jvn.jp/en/jp/JVN35265756/)