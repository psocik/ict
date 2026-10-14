---
title: Swann Communications SWIFI-SE2KIC Vulnerabilities
date: 2026-10-13
categories: [SECURITY]
tags: [SWANN,VULNERABILITIES,SECURITY,CISA]
---

## Swann Communications SWIFI-SE2KIC Vulnerabilities

**Date Published:** October 13, 2026  
**Source:** CISA  

Successful exploitation of these vulnerabilities could allow an attacker to view video information without authentication. The following versions of Swann Communications SWIFI-SE2KIC are affected: SWIFI-SE2KIC firmware <=2.0.22 (CVE-2026-107605, CVE-2026-107606, CVE-2026-107607). These devices are deployed worldwide and are used in Critical Infrastructure Sectors: Commercial Facilities. Elliott Phillips reported these vulnerabilities to CISA.

### Vulnerabilities Overview
- **CVE-2026-107605:** Missing Authentication for Critical Function vulnerability that could allow an attacker on the local network to view live video feed without authentication.
- **CVE-2026-107606:** Missing Authentication for Critical Function vulnerability that could allow an attacker on the local network to retrieve a snapshot of the live feed without authentication.
- **CVE-2026-107607:** Missing Authentication for Critical Function vulnerability that could allow an attacker on the local network to access a real-time video stream without authentication.

These vulnerabilities are not exploitable remotely.

### Interim Security Measures
Swann Communications has provided the following interim security measures:
- Keep the camera behind a secured router and firewall.
- Avoid exposing RTSP services to the internet through port forwarding, DMZ configurations, or direct public IP access.
- Ensure the router and associated accounts use strong, unique passwords.
- Keep device firmware updated when new releases become available.

CISA recommends users take defensive measures to minimize the risk of exploitation of these vulnerabilities, including minimizing network exposure for all control system devices and ensuring they are not accessible from the internet. Locate control system networks and remote devices behind firewalls and isolate them from business networks. When remote access is required, use more secure methods, such as Virtual Private Networks (VPNs), recognizing that VPNs may have vulnerabilities and should be updated to the most current version available.

No known public exploitation specifically targeting these vulnerabilities has been reported to CISA at this time.

[Read full article](https://www.cisa.gov/news-events/ics-advisories/icsa-26-286-02)  
