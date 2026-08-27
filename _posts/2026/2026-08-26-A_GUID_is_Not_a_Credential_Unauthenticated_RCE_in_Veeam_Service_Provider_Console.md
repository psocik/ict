---
title: A GUID is Not a Credential Unauthenticated RCE in Veeam Service Provider Console
date: 2026-08-26
categories: [SECURITY]
tags: [VEEAM,RCE,VULNERABILITIES,SECURITY]
---

## A GUID is Not a Credential: Unauthenticated RCE in Veeam Service Provider Console

🚨 **Critical Vulnerabilities Identified!** 🚨

CVE-2026-58073 (CVSS 9.5) and CVE-2026-58072 (CVSS 9.0) are critical vulnerabilities in the Veeam Service Provider Console, a multi-tenant console used by managed service providers to run backups for their customers. 

### Vulnerability Details
- **CVE-2026-58073**: This vulnerability allows an unauthenticated network peer to claim a connected backup agent's identity and receive that agent's real certificate.
- **CVE-2026-58072**: This vulnerability enables anyone holding an agent certificate to write a file anywhere on the server.

When combined, these vulnerabilities lead to unauthenticated remote code execution on the console, which manages backups for all tenants. 

On **August 4, 2026**, Veeam published KB4893, addressing four vulnerabilities in the Veeam Service Provider Console (VSPC). All four vulnerabilities affect version 9.2.1.33875 and earlier builds. The fix is available only in version 9.3.0.35057, requiring a version upgrade for remediation.

### How the Exploitation Works
For CVE-2026-58073, the server checks if a connection is authenticated by asking if someone with a specific GUID has logged in previously. This check is not tied to the certificate presented, allowing an unauthenticated peer to exploit the system. 

CVE-2026-58072 allows an attacker to upload files to arbitrary locations on the server without validation, leading to potential code execution.

### Recommendations
- **Patch** to version 9.3.0 or later.
- **Restrict access** to TCP/9999; only allow connections from subnets where agents reside.
- **Run detection tools** against all consoles to identify potential exploitation.

For further details, read the full article here: [Read full article](https://bishopfox.com/blog/a-guid-is-not-a-credential-unauthenticated-rce-in-veeam-service-provider-console)