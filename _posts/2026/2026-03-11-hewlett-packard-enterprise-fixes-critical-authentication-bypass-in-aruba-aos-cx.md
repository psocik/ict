---
title: Hewlett Packard Enterprise Fixes Critical Authentication Bypass in Aruba AOS-CX
date: 2026-03-11
categories: [SECURITY]
tags: [HEWLETT PACKARD,ARUBA,AUTHENTICATION,VULNERABILITY,SECURITY]
---

## Hewlett Packard Enterprise Fixes Critical Authentication Bypass in Aruba AOS-CX 🚀

Hewlett Packard Enterprise (HPE) has addressed several vulnerabilities in Aruba AOS-CX, including a **critical bug** that allows attackers to reset admin passwords. The most severe issue, tracked as **CVE-2026-23813** (CVSS score of 9.8), enables unprivileged attackers to bypass authentication and reset administrator passwords through a low-complexity attack.

> "A vulnerability has been identified in the web-based management interface of AOS-CX switches that could potentially allow an unauthenticated remote actor to circumvent existing authentication controls. In some cases, this could enable resetting the admin password," reads the advisory.

To mitigate the risks associated with **CVE-2026-23813**, HPE recommends:
- Isolating management interfaces on a dedicated VLAN
- Limiting access only to trusted hosts
- Disabling unnecessary HTTP/HTTPS management interfaces
- Enforcing ACLs for REST/HTTPS access
- Enabling logging and monitoring to quickly detect unauthorized activity

The researcher **moonv** reported the vulnerability through HPE Aruba Networking’s Bug Bounty program.

### Additional Vulnerabilities Addressed
HPE also fixed the following vulnerabilities:
- **CVE-2026-23814** (CVSS score of 8.8): Authenticated Command Injection in AOS-CX CLI command allows low-privilege remote attackers to inject malicious commands, leading to arbitrary code execution.
- **CVE-2026-23815** (CVSS score of 7.2): Authenticated Command Injection in high-privilege AOS-CX CLI custom binary enables remote attackers to execute unauthorized OS commands.
- **CVE-2026-23816** (CVSS score of 7.2): Authenticated Command Injection in AOS-CX CLI allows remote attackers to execute arbitrary OS commands via crafted input.
- **CVE-2026-23817** (CVSS score of 6.5): Unauthenticated Open Redirect in AOS-CX web interface enables remote attackers to redirect users to arbitrary malicious URLs, potentially leading to phishing attacks.

HPE Aruba Networking has no evidence of attacks exploiting these vulnerabilities in the wild. The advisory states, "HPE Aruba Networking is not aware of any public discussion or exploit code targeting these specific vulnerabilities as of the release date of the advisory."

In July 2025, HPE disclosed hardcoded credentials in Aruba Instant On Wi-Fi devices that allow attackers to bypass login and access the web interface. This flaw, tracked as **CVE-2025-37103** (CVSS score of 9.8), impacts devices running firmware version 3.2.0.1 and below. 

> "Hardcoded login credentials were found in HPE Networking Instant On Access Points, allowing anyone with knowledge of it to bypass normal device authentication," reads the advisory. "Successful exploitation could allow a remote attacker to gain administrative access to the system."

For more details, [Read full article](https://securityaffairs.com/189278/security/hewlett-packard-enterprise-fixes-critical-authentication-bypass-in-aruba-aos-cx.html)