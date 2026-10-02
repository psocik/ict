---
title: Vulnerabilities in Monta monta.app Exposed
date: 2026-10-01
categories: [SECURITY]
tags: [MONTA,VULNERABILITIES,SECURITY,CISA]
---

## Vulnerabilities in Monta monta.app Exposed

🚨 **Attention!** Successful exploitation of these vulnerabilities could enable attackers to gain unauthorized administrative control over vulnerable charging stations or disrupt charging services through denial-of-service attacks.

### Affected Versions
The following versions of Monta monta.app are affected:
- monta.app vers: all/* 
- CVE-2026-95102
- CVE-2026-97363
- CVE-2026-97212
- CVE-2026-93474

### Impact
These vulnerabilities impact Critical Infrastructure Sectors including Energy and Transportation Systems, with deployments worldwide. An anonymous researcher reported these vulnerabilities to CISA.

### Detailed Vulnerabilities
- **CVE-2026-95102**: WebSocket endpoints lack proper authentication mechanisms, enabling attackers to impersonate charging stations. This weakness can lead to unauthorized access to sensitive data or unauthorized actions, compromising the entire system's security.
- **CVE-2026-97363**: The WebSocket API lacks restrictions on the number of authentication requests, allowing denial-of-service or brute-force attacks.
- **CVE-2026-97212**: The WebSocket backend uses charging station identifiers for session association but allows multiple endpoints to connect using the same session identifier, leading to predictable session identifiers.
- **CVE-2026-93474**: Charging station authentication identifiers are publicly accessible via web-based mapping platforms.

### Mitigation Measures
Monta states that they are actively working to increase adoption of authenticated connections across their network and to deprecate unauthenticated access on a rolling basis. They provide support for OCPP 1.6 Security Profile 2 (HTTP Basic Auth with TLS) and encourage operators to enable it. Monta has also implemented rate limiting and automated connection throttling at the WebSocket layer to block abusive patterns.

### Recommendations from CISA
CISA recommends users take defensive measures to minimize the risk of exploitation, including:
- Minimizing network exposure for all control system devices.
- Ensuring devices are not accessible from the Internet.
- Locating control system networks and remote devices behind firewalls.
- Using more secure methods for remote access, such as Virtual Private Networks (VPNs).

No known public exploitation specifically targeting these vulnerabilities has been reported to CISA at this time.

For more information, [Read full article](https://www.cisa.gov/news-events/ics-advisories/icsa-26-274-02) 
