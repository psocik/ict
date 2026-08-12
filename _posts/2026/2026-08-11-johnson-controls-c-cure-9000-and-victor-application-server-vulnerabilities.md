---
title: Johnson Controls C-CURE 9000 and Victor Application Server Vulnerabilities
date: 2026-08-11
categories: [CYBERSECURITY]
tags: [VULNERABILITIES,CYBERSECURITY,JOHNSON-CONTROLS,C-CURE,VICTOR]
---

## Johnson Controls C-CURE 9000 and Victor Application Server Vulnerabilities 🚨

On **August 11, 2026**, CISA published an advisory regarding critical vulnerabilities in the Johnson Controls C-CURE 9000 and Victor application server. Successful exploitation of these vulnerabilities could allow an attacker with network access to achieve **remote code execution**. The affected versions include:

- **C-CURE 9000** <= v3.10.1 (CVE-2026-21655)
- **Victor Application Server** <= v4.10 (CVE-2026-21655)
- **Victor** <= v7.0 (CVE-2026-21655)
- **Victor Web** <= v7.1 (CVE-2026-34496)

These vulnerabilities pose a significant risk to critical manufacturing sectors worldwide. Harrison Neal reported these vulnerabilities to CISA.

### Key Vulnerabilities

1. **CVE-2026-21655**: Allows an unauthenticated attacker on an adjacent network to achieve arbitrary code execution on the C-CURE 9000 and Victor application server, impacting physical security controls.
2. **CVE-2026-21653**: Could allow an attacker to forge server-side HTTP requests from the Victor Web application, leading to unauthorized information disclosure.
3. **CVE-2026-34496**: May enable low privilege users to access unauthorized pages, potentially allowing further attacks or unauthorized administrative actions.

### Recommendations

Johnson Controls recommends the following defensive measures to mitigate these risks:
- Implement strict firewall rules to block unnecessary inbound connections to port 8999 from untrusted network segments.
- Deploy IDS/IPS signatures to detect known .NET deserialization exploit payloads targeting port 8999.
- Enforce application whitelisting on application server hosts.
- Ensure the application server process runs with minimum privileges.
- Enable detailed logging on application server hosts and monitor for anomalous process creation.

For more detailed mitigation instructions, please refer to Johnson Controls Product Security Advisories JCI-PSA-2026-07, JCI-PSA-2026-13, and JCI-PSA-2026-16.

CISA urges users to take defensive measures to minimize the risk of exploitation of these vulnerabilities. For the complete article, see: [Read full article](https://www.cisa.gov/news-events/ics-advisories/icsa-26-204-01)