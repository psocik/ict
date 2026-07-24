---
title: MZ Automation libIEC61850 Vulnerabilities Exposed
date: 2026-07-23
categories: [CYBERSECURITY]
tags: [VULNERABILITIES,AUTOMATION,CYBERSECURITY,CISA]
---

## MZ Automation libIEC61850 Vulnerabilities Exposed

🚨 **Critical Alert!** Successful exploitation of these vulnerabilities could allow an unauthenticated network-adjacent attacker to crash critical IEC 61850 services or execute arbitrary code, disrupting or compromising protection, visibility, and control functions.

The following versions of MZ Automation libIEC61850 are affected: **libIEC61850 >=v1.0.0** and **<=v1.6.1**. These vulnerabilities impact critical sectors including **Manufacturing**, **Energy**, and **Transportation** worldwide. Abhinav Agarwal reported these vulnerabilities to CISA.

### Vulnerabilities Identified:
- **CVE-2026-50039**: Stack-based buffer overflow, allowing memory corruption via a ReadRequest.
- **CVE-2026-49035**: Heap-based buffer overflow via a crafted MMS Initiate request.
- **CVE-2026-50103**: NULL pointer dereference affecting the L2 GOOSE and R-GOOSE shared parser, potentially crashing a subscribing application.
- **CVE-2026-50032**: Another NULL pointer dereference in the MMS Write Named Variable List handler, which may crash the server.

### Recommendations:
MZ Automation recommends updating to the latest build of the libIEC61850 standard. CISA advises users to take defensive measures to minimize the risk of exploitation:
- Minimize network exposure for all control system devices.
- Ensure devices are not accessible from the internet.
- Use firewalls to isolate control system networks.
- When remote access is necessary, utilize secure methods like **VPNs**.

CISA emphasizes the importance of conducting proper impact analysis and risk assessment before deploying defensive measures. As of now, no known public exploitation specifically targeting these vulnerabilities has been reported to CISA.

For more details, [Read full article](https://www.cisa.gov/news-events/ics-advisories/icsa-26-204-06).