---
title: Multiple Vulnerabilities in XING CPTrans-ME-X
date: 2026-09-04
categories: [SECURITY]
tags: [XING,VULNERABILITIES,SECURITY,FIRMWARE]
---

## Multiple Vulnerabilities in XING CPTrans-ME-X 🚨

XING CPTrans-ME-X contains multiple vulnerabilities that pose significant security risks. Specifically, firmware versions prior to Ver 1.8.1.17 are affected. These vulnerabilities include:

- **OS Command Injection**
- **Exposure of Sensitive System Information to an Unauthorized Control Sphere**
- **Use of Default Password**
- **Use of Hard-coded Password**

### Critical Vulnerabilities 🔍
One critical vulnerability is OS Command Injection (CWE-78), tracked as **CVE-2026-62928**. This flaw has a CVSSv4.0 Base Score of **9.3** and a CVSSv3.0 Base Score of **9.8**. Improper processing of the input through the administrative port may lead to OS command injection.

Additionally, **CVE-2026-66840** addresses an Exposure of Sensitive System Information to an Unauthorized Control Sphere (CWE-497), with a CVSSv4.0 Base Score of **8.7** and a CVSSv3.0 Base Score of **7.5**. This vulnerability also results from improper input processing through the administrative port.

### Authentication Vulnerabilities 🔑
Furthermore, XING CPTrans-ME-X is susceptible to vulnerabilities related to authentication. **CVE-2026-69657** details a Use of Default Password (CWE-1393), with a CVSSv4.0 Base Score of **9.3** and a CVSSv3.0 Base Score of **9.8**. Affected devices with the initial configuration have a default password for the Web UI. A related issue, **CVE-2026-70403**, concerns the Use of Hard-coded Password (CWE-259), also with a CVSSv4.0 Base Score of **9.3** and a CVSSv3.0 Base Score of **9.8**. This flaw allows unauthorized users to log in to the administrative port due to an embedded password in the firmware.

### Impact and Mitigation ⚠️
The impact of these vulnerabilities includes unauthenticated OS command injection, sensitive system information exposure, and unauthorized access to the affected device. To mitigate these risks, users are advised to update the firmware. At the time of this JVN advisory publishing, the developer provides a firmware update to narrow the attack surface. This update ensures that the administrative port is disabled in the initial configuration and limits the set of commands available when logged in to only those necessary for maintenance purposes.

These issues were reported by Katsuhiko Sato (a.k.a. goroh_kun) of 00One, Inc. to IPA, with JPCERT/CC coordinating with the developer under the Information Security Early Warning Partnership.

For more details, [Read full article](https://jvn.jp/en/jp/JVN32505330/).