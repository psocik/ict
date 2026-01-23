---
title: Vulnerabilities in EVMAPA
date: 2026-01-22
categories: [VULNERABILITIES]
tags: [VULNS,EVMAPA,ICS-CERT ADVISORIES,CYBERSECURITY]
---

**Title:** EVMAPA  
**Source:** ICS-CERT Advisories  
**Date Published:** January 22, 2026  
  
Successful exploitation of these vulnerabilities could lead to degraded service, a denial-of-service, or unauthorized remote command execution, which could lead to spoofing or a manipulation of charging station statuses. The following versions of EVMAPA are affected: EVMAPA (CVE-2025-54816, CVE-2025-53968, CVE-2025-55705). These vulnerabilities impact Critical Infrastructure Sectors, specifically Transportation Systems, with deployments in Czechia and Slovakia.  
  
- **CVE-2025-54816** (CWE-306 Missing Authentication for Critical Function): Occurs when a WebSocket endpoint does not enforce proper authentication mechanisms, allowing unauthorized users to establish connections. Attackers can exploit this weakness to gain unauthorized access to sensitive data or perform unauthorized actions, leading to privilege escalation and potentially compromising system security.  
- **CVE-2025-53968** (CWE-307 Improper Restriction of Excessive Authentication Attempts): There are no limitations on the number of authentication attempts a user can make, allowing attackers to overwhelm the authentication system, leading to denial-of-service (DoS) conditions and potential brute-force attacks.  
- **CVE-2025-55705** (CWE-613 Insufficient Session Expiration): This vulnerability occurs when the system allows multiple simultaneous connections using the same charging station ID, which can result in unauthorized access and data inconsistency.  
  
CISA recommends taking defensive measures to minimize the risk of exploitation of these vulnerabilities, which include minimizing network exposure for all control system devices, ensuring they are not accessible from the Internet, locating control system networks behind firewalls, and using secure remote access methods such as Virtual Private Networks (VPNs).  
  
**To read the complete article, visit:** [CISA Advisory](https://www.cisa.gov/news-events/ics-advisories/icsa-26-022-08)  
