---
title: StoneFly Storage Concentrator Vulnerabilities Exposed
date: 2026-06-30
categories: [SECURITY]
tags: [STONEFLY,VULNERABILITIES,SECURITY,CISA]
---

## StoneFly Storage Concentrator Vulnerabilities Exposed

🚨 **Critical Security Alert!** 🚨

Successful exploitation of these vulnerabilities could allow attackers to gain broad unauthorized access, execute arbitrary commands with root privileges, steal sensitive data, and perform actions on behalf of legitimate users across interconnected systems. The following versions of StoneFly Storage Concentrator are affected:

- **Storage Concentrator < 8.0.4.22** (CVE-2026-56415, CVE-2026-55721, CVE-2026-50040)
- **Storage Concentrator Virtual Machine < 8.0.4.22** (CVE-2026-56415, CVE-2026-55721, CVE-2026-50040)
- **Storage Concentrator < 8.0.4.26** (CVE-2026-50110)
- **Storage Concentrator Virtual Machine < 8.0.4.26** (CVE-2026-50110)
- **Storage Concentrator < 8.0.4.29** (CVE-2026-56413)
- **Storage Concentrator Virtual Machine < 8.0.4.29** (CVE-2026-56413)

### Vulnerabilities Overview

1. **CVE-2026-50110**: Hardcoded credentials vulnerability in Storage Concentrator (SC & SCVM). Numerous internal services have credentials embedded within a configuration file, which, while encoded, can be reversed to plaintext. This could provide unauthorized access to multiple interconnected systems.

2. **CVE-2026-56413**: Command injection vulnerability impacting the ms_service.pl service, allowing unauthenticated remote attackers to execute arbitrary commands with root-level privileges.

3. **CVE-2026-56415**: Command injection vulnerability within the debug.pl script, reachable without authentication, leading to arbitrary command execution.

4. **CVE-2026-55721**: SQL injection vulnerability through cookie values processed by login.pl and debug.pl scripts, allowing attackers to manipulate database queries.

5. **CVE-2026-50040**: Reflected cross-site scripting (XSS) vulnerability due to unsanitized content in 404 error pages.

### Recommendations

StoneFly recommends that users upgrade to Storage Concentrator version 8.0.4.29 or later to remediate these vulnerabilities. 

For more detailed information, you can read the full article here: [Read full article](https://www.cisa.gov/news-events/ics-advisories/icsa-26-181-06)