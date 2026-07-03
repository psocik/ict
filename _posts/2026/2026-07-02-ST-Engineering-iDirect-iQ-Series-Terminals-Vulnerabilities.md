---
title: ST Engineering iDirect iQ-Series Terminals Vulnerabilities
date: 2026-07-02
categories: [CYBERSECURITY]
tags: [VULNERABILITIES,CYBERSECURITY,IDIRECT,ST ENGINEERING,CISA]
---

## ST Engineering iDirect iQ-Series Terminals Vulnerabilities 🚨

**Date Published:** July 2, 2026

Successful exploitation of these vulnerabilities could allow an attacker to gain unauthorized access to device information or cause a denial-of-service condition. ST Engineering iDirect has fixed vulnerabilities affecting Evolution iQ-Series terminals (<= 4.5.2.1), 3315-Series terminals (<= 4.5.2.1), and 9-Series terminals (<= 4.5.2.1). These vulnerabilities, identified as CVE-2026-38059 and CVE-2026-38057, are deployed worldwide and impact critical infrastructure sectors including Communications, Defense Industrial Base, Energy, Government Services and Facilities, and Transportation Systems. No known public exploitation specifically targeting these vulnerabilities has been reported to CISA at this time.

### Vulnerability Details 🔍

- **CVE-2026-38059:** Classified as CWE-306 Missing Authentication for Critical Function, specifically affects the iDirect iQ200. This vulnerability exposes the `/api/identity` and `/api/` REST API endpoints without authentication. An unauthenticated attacker with network access can retrieve sensitive device information including the serial number, Device ID (DID), Terminal Private Key identifier (TPK), MAC address, and exact firmware version. The DID and TPK are used for satellite network authentication in the iDirect platform, potentially enabling terminal impersonation and network reconnaissance.

- **CVE-2026-38057:** Involves the iDirect iQ200 not validating CSRF tokens on state-changing API endpoints after authentication. The `/api/reboot` endpoint accepts POST requests authenticated solely by a session cookie that lacks the SameSite attribute. A remote attacker can host a malicious web page that, when visited by an authenticated administrator, automatically submits a cross-site POST request causing an immediate device reboot and satellite link loss. Repeated attacks can sustain a denial-of-service condition.

### Recommendations 🛡️

For remediation, ST Engineering iDirect recommends users update the software to version 4.5.2.2 or newer. Registered users can download patches from the iDirect Support Portal. Further mitigation measures include:
- Restricting management interfaces to trusted networks (e.g., VPN, ACLs).
- Avoiding exposing administrative APIs to the public internet.
- Enforcing strong authentication practices and monitoring for anomalous API activity.

CISA further recommends minimizing network exposure for all control system devices and ensuring they are not accessible from the internet. Locating control system networks and remote devices behind firewalls and isolating them from business networks is also advised. When remote access is required, use more secure methods, such as Virtual Private Networks (VPNs).

For more details, please visit the full article: [Read full article](https://www.cisa.gov/news-events/ics-advisories/icsa-26-183-01)