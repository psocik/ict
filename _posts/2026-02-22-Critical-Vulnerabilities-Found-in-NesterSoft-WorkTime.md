---
title: Critical Vulnerabilities Found in NesterSoft WorkTime
date: 2026-02-22
categories: [SECURITY]
tags: [NESTERSOFT,VULNERABILITIES,SECURITY,CVE]
---

## SEC Consult Security Advisory

SEC Consult Vulnerability Lab has issued a security advisory detailing multiple critical vulnerabilities in **NesterSoft WorkTime** (on-prem/cloud), impacting vulnerable versions <= 11.8.8. The advisory notes that **no patch is available, and the vendor is unresponsive**, making the impact critical. 🚨

### Identified Vulnerabilities
- **CVE-2025-15559**: Unauthenticated OS Command Injection. An unauthenticated attacker can inject OS commands when calling a server API endpoint, allowing them to execute arbitrary commands on the WorkTime server with the highest privileges. This vulnerability can lead to sensitive data manipulation and server takeover.
- **CVE-2025-15560**: SQL Injection affecting MSSQL/Firebird backends. An authenticated attacker can exploit this vulnerability to inject SQL queries, potentially retrieving all data from the database.
- **CVE-2025-15561**: Local Privilege Escalation, allowing attackers to elevate privileges on the local system.
- **CVE-2025-15562**: Reflected Cross-Site Scripting (XSS) vulnerability, enabling attackers to execute arbitrary JavaScript in victims' browsers.
- **CVE-2025-15563**: Broken Access Control resulting in Denial of Service, allowing any unauthenticated user to reset the WorkTime on-prem database configuration.

### Recommendations
SEC Consult highly recommends performing a thorough security review of the product conducted by security professionals to identify and resolve potential further security issues. 🔍

For more details, read the complete article [here](https://seclists.org/fulldisclosure/2026/Feb/31).