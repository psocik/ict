---
title: Dorsett Controls InfoScan Vulnerabilities
date: 2026-11-17
categories: [SECURITY]
tags: [DORSETT,INFSCAN,VULNERABILITIES,SECURITY,CISA]
---

## Dorsett Controls InfoScan Vulnerabilities

Dorsett Controls has reported significant vulnerabilities in their InfoScan application that could lead to serious security issues. 🚨

### Key Vulnerabilities:
- **CVE-2026-117659 (CWE-295)**: The InfoScan Electron desktop client improperly handles TLS certificate errors, allowing attackers to present untrusted certificates without rejection.
- **CVE-2026-120157 (CWE-497)**: The publicly distributed InfoScan Electron installer contains configuration files that expose hostnames associated with customer installations.
- **CVE-2026-120255 (CWE-321)**: Hard-coded cryptographic keys in the database-encryption implementation could allow recovery of sensitive information.
- **CVE-2026-120260 (CWE-306)**: Lack of authentication on an endpoint allows local attackers to retrieve sales-automation templates.
- **CVE-2026-120271**: An unauthenticated information disclosure vulnerability allows remote attackers to access system configuration data.

### Recommended Action:
Dorsett Controls advises all users to update affected versions of InfoScan to version 1.46 or higher. To install the security patch:
1. Log in to InfoScan.
2. Select **System Maintenance** from the menu.
3. Click **Check for Updates** and then **Install Now**.

For offline customers, updates can be downloaded from the Dorsett Controls Customer Portal.

For more details, read the full article here: [Read full article](https://www.cisa.gov/news-events/ics-advisories/icsa-26-321-01) 

Stay safe and secure! 🔒