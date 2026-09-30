---
title: Multiple Vulnerabilities in Pgpool-II
date: 2026-09-29
categories: [SECURITY]
tags: [VULNERABILITIES,PGPOOL,SECURITY,CVE]
---

## Multiple Vulnerabilities in Pgpool-II 🚨

Pgpool-II, provided by the Pgpool Global Development Group, has been found to contain multiple vulnerabilities, as reported under JVN#22475874 and published on **September 29, 2026**. These vulnerabilities affect a wide range of Pgpool-II versions, including:
- 4.7.0 to 4.7.2
- 4.6.0 to 4.6.7
- 4.5.0 to 4.5.12
- 4.4.0 to 4.4.17
- 4.3.0 to 4.3.20

Additionally, all versions from the Pgpool-II 3.5.x series through 4.2.x series are impacted.

### Identified Vulnerabilities 🔍
The vulnerabilities include:
- **CVE-2026-92867**: Out-of-bounds Write (CWE-787) - CVSS 4.0 Base Score: 8.7
- **CVE-2026-92868**: Improper Certificate Validation (CWE-295) - CVSS 4.0 Base Score: 6.9
- **CVE-2026-92869**: Out-of-bounds Write (CWE-787) - CVSS 4.0 Base Score: 7.1
- **CVE-2026-92870**: Stack-based Buffer Overflow (CWE-121) - CVSS 4.0 Base Score: 8.7
- **CVE-2026-92871**: NULL Pointer Dereference (CWE-476) - CVSS 4.0 Base Score: 8.7
- **CVE-2026-92872**: Insertion of Sensitive Information into Log File (CWE-532) - CVSS 4.0 Base Score: 5.3
- **CVE-2026-92873**: Incorrect Implementation of Authentication Algorithm (CWE-303) - CVSS 4.0 Base Score: 6.9

### Impact ⚠️
These vulnerabilities carry significant impacts:
- **CVE-2026-92867** can lead to abnormal process termination and arbitrary code execution.
- **CVE-2026-92868** allows for client certificate authentication bypass.
- **CVE-2026-92869** and **CVE-2026-92870** can cause abnormal process termination.
- **CVE-2026-92871** leads to abnormal termination of the watchdog process.
- **CVE-2026-92872** can result in a cluster information leak.
- **CVE-2026-92873** enables the promotion of an arbitrary watchdog node to the leader node.

### Recommended Actions 🔧
To address these vulnerabilities, users are advised to update the software to the latest version. The following versions have been released to mitigate these vulnerabilities:
- Pgpool-II 4.7.3
- Pgpool-II 4.6.8
- Pgpool-II 4.5.13
- Pgpool-II 4.4.18
- Pgpool-II 4.3.21

These vulnerabilities were reported by **Emond Papegaaij** of Topicus Security to the Pgpool Global Development Group.

For more details, you can read the complete article here: [Read full article](https://jvn.jp/en/jp/JVN22475874/).