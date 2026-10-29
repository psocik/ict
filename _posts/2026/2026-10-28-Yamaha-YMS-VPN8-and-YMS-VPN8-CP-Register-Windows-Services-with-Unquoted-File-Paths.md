---
title: Yamaha YMS-VPN8 and YMS-VPN8-CP Register Windows Services with Unquoted File Paths
date: 2026-10-28
categories: [SECURITY]
tags: [YAMAHAS,WINDOWS,VULNERABILITY,CVE,CYBERSECURITY]
---

## Yamaha YMS-VPN8 and YMS-VPN8-CP Vulnerability Alert 🚨

**Date Published:** October 28, 2026  
**Source:** JVN  

JVN#30675482 indicates that **Yamaha YMS-VPN8** and **YMS-VPN8-CP** register Windows services with unquoted file paths. These products, provided by Yamaha Corporation, contain the following vulnerability: **Unquoted search path or element (CWE-428)**. This vulnerability is tracked as **CVE-2026-97860**. 

### Affected Products:
- YMS-VPN8 versions Ver.1.04.00 and earlier  
- YMS-VPN8-CP versions Ver.1.04.00 and earlier  

### Vulnerability Impact:
The vulnerability has been assigned a **CVSS:4.0 Base Score of 8.4** with the vector `AV:L/AC:L/AT:N/PR:H/UI:N/VC:H/VI:H/VA:H/SC:N/SI:N/SA:N`. A **CVSS:3.0 Base Score of 6.7** has also been provided. The impact states that a user who has write permissions on the system drive may be able to execute arbitrary code with **SYSTEM** privileges.

### Recommended Solutions:
Users are advised to:
- **Update the Software:** Update to the latest version according to the information provided by the developer. The following versions have been released to fix the vulnerability:
  - YMS-VPN8 Ver.1.07.00  
  - YMS-VPN8-CP Ver.1.07.00  
- **Apply the Workaround:** For users who cannot update the software, the developer recommends the following mitigations:
  - Do not share the Windows PC with other users.
  - Do not allow untrusted users to log in.
  - Do not grant administrative privileges to users who do not require them.
  - Do not execute files or programs from unknown or untrusted sources.

### Reporting:
Kazuma Matsumoto of GMO Cybersecurity by IERAE, Inc. reported this vulnerability to IPA. JPCERT/CC coordinated with the developer under the Information Security Early Warning Partnership.

For more details, you can read the complete article here: [Read full article](https://jvn.jp/en/jp/JVN30675482/)  
