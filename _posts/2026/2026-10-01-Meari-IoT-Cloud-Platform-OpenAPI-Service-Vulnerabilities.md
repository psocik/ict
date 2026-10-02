---
title: Meari IoT Cloud Platform OpenAPI Service Vulnerabilities
date: 2026-10-01
categories: [SECURITY]
tags: [MEARI,IOT,VULNERABILITIES,CISA]
---

## Meari IoT Cloud Platform OpenAPI Service Vulnerabilities

🚨 **Critical Alert:** Successful exploitation of vulnerabilities in the Meari IoT Cloud Platform OpenAPI Service could allow attackers to manipulate device configurations, trigger unauthorized behaviors, and access sensitive information such as device credentials, owner details, and network data without proper authorization.

### Affected Versions
The vulnerabilities affect the Meari IoT Cloud Platform OpenAPI Service, specifically versions: all/*, and are identified as CVE-2026-101104 and CVE-2026-96613. These issues impact critical infrastructure sectors, including Commercial Facilities and Information Technology, with deployed systems worldwide.

### Vulnerability Details
- **CVE-2026-101104:** An authorization flaw that allows authenticated users to manipulate configurations of devices they do not own, enabling unauthorized actions like altering device settings.
- **CVE-2026-96613:** Another authorization flaw that allows authenticated users to access the complete device shadow of any device by specifying its device ID, exposing sensitive information without verifying any relationship between the requester and the target device.

Both vulnerabilities are classified under **CWE-862**, Missing Authorization. Unfortunately, no fix is planned for these vulnerabilities, and Meari has not responded to CISA's coordination attempts.

### Recommendations
CISA recommends users take defensive measures to minimize the risk of exploitation:
- Minimize network exposure for all control system devices and ensure they are not accessible from the internet.
- Locate control system networks and remote devices behind firewalls and isolate them from business networks.
- When remote access is required, use more secure methods such as **Virtual Private Networks (VPNs)**, and ensure they are updated to the most current version available.

Organizations should perform proper impact analysis and risk assessment prior to deploying defensive measures. If you observe suspected malicious activity, follow established internal procedures and report findings to CISA for tracking and correlation against other incidents.

No known public exploitation specifically targeting these vulnerabilities has been reported to CISA at this time.

For more details, read the full article here: [Read full article](https://www.cisa.gov/news-events/ics-advisories/icsa-26-274-06)\n