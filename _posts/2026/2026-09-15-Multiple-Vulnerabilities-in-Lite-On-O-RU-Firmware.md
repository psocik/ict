---
title: Multiple Vulnerabilities in Lite-On O-RU Firmware
date: 2026-09-15
categories: [SECURITY]
tags: [VULNERABILITIES,LITE-ON,FIRMWARE,SECURITY,CVE]
---

## Multiple Vulnerabilities in Lite-On O-RU Firmware

Lite-On Technology Corporation has reported multiple vulnerabilities in their O-RU models "FF-RFI079I4" and "FF-RFI078I4". These vulnerabilities affect firmware versions prior to v02.01.15. The Japan Vulnerability Notes (JVN) has identified these issues under JVN#02049764.

### Identified Vulnerabilities
- **OS Command Injection (CWE-78)**: 
  - Tracked as **CVE-2026-77853** with a CVSS Base Score of 8.7.
  - Users who can log into the product's M-Plane (NETCONF) may execute arbitrary OS commands.

- **Hidden Functionality (CWE-912)**: 
  - Tracked as **CVE-2026-80217** with a CVSS Base Score of 8.7.
  - Users who can log in via SSH and access enable mode may also execute arbitrary OS commands.

### Recommended Actions
To mitigate these vulnerabilities, it is crucial for users to update their firmware to the latest version as advised by the developer. This update will help secure the devices against potential exploits.

These vulnerabilities were reported to the developer and coordinated by Yuto Aono, Yutaro Osako, and Shunsuke Saruwatari from The University of Osaka. They also reported the case to JPCERT/CC to ensure users are notified of the solution through JVN.

For more details, please read the complete article here: [Read full article](https://jvn.jp/en/jp/JVN02049764/) 

🚀 Stay safe and keep your systems updated!