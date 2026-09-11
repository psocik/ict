---
title: Multiple Vulnerabilities in SolarView Compact
date: 2026-09-10
categories: [SECURITY]
tags: [VULNERABILITIES,SOLARVIEW,CONTEC,SECURITY,FIRMWARE]
---

## Multiple Vulnerabilities in SolarView Compact 🚨

SolarView Compact, provided by Contec Co., Ltd., contains multiple vulnerabilities that affect various product versions. The affected products include:
- **SolarView Compact**
- **SV-CPT-MC310** versions prior to 9.00
- **SV-CPT-MC310F** versions prior to 9.00

### Vulnerability Details 🔍
1. **OS Command Injection** (CWE-78)
   - **CVE-2026-82794**
   - **CVSSv4.0 Base Score:** 8.7
   - **CVSSv3.1 Base Score:** 8.8
   - **Impact:** An arbitrary OS command may be executed by an attacker who can log in to the product.

2. **Cross-Site Scripting Vulnerabilities** (CWE-79)
   - **CVE-2026-82795** (Schedule Settings and Mail Send Setting)
     - **CVSSv4.0 Base Score:** 5.1
     - **CVSSv3.1 Base Score:** 5.4
   - **CVE-2026-82796** (Image Management)
     - **CVSSv4.0 Base Score:** 5.1
     - **CVSSv3.1 Base Score:** 5.4
   - **Impact:** An arbitrary script may be executed on a logged-in user's web browser.

### Recommended Action ⚠️
To mitigate these issues, users are advised to update the firmware to the latest version as per the information provided by the developer. Contec Co., Ltd. has reported these vulnerabilities to JPCERT/CC to notify users of the solutions through JVN.

For more details, you can read the complete article here: [Read full article](https://jvn.jp/en/vu/JVNVU97753461/) 
