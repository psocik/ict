---
title: HMS Networks PEAK-System PCAN Windows Drivers Vulnerabilities
date: 2026-10-20
categories: [CYBERSECURITY]
tags: [HMS,PCAN,WINDOWS,DRIVERS,VULNERABILITIES,CYBERSECURITY]
---

## HMS Networks PEAK-System PCAN Windows Drivers Vulnerabilities 🚨

On **October 20, 2026**, CISA published a critical advisory regarding vulnerabilities in the HMS Networks PEAK-System PCAN Windows drivers. Successful exploitation of these vulnerabilities could lead to a crash of the Windows kernel. The affected versions include:

- **PEAK-System Device Driver Setup** <= 5.1.2.1151  
  (CVE-2026-109576, CVE-2026-101103, CVE-2026-94188, CVE-2026-103672, CVE-2026-110322, CVE-2026-105960)
- **PCAN Windows CAN device drivers** <= 5.1.2  
  (CVE-2026-109576, CVE-2026-101103, CVE-2026-94188, CVE-2026-103672, CVE-2026-110322, CVE-2026-105960)

These vulnerabilities impact critical infrastructure sectors including **Transportation Systems**, **Healthcare and Public Health**, **Energy**, and **Critical Manufacturing**. They are deployed worldwide, but no known public exploitation has been reported to CISA at this time.

### Recommended Defensive Measures 🔒
CISA recommends users take defensive measures to minimize the risk of exploitation:
- Minimize network exposure for all control system devices and systems.
- Ensure they are not accessible from the internet.
- Locate control system networks and remote devices behind firewalls and isolate them from business networks.
- When remote access is required, use secure methods such as **Virtual Private Networks (VPNs)**.

CISA also emphasizes the importance of performing proper impact analysis and risk assessment prior to deploying defensive measures. For more detailed guidance, visit the [CISA ICS webpage](https://www.cisa.gov/ics).

Organizations observing suspected malicious activity should follow established internal procedures and report findings to CISA for tracking and correlation against other incidents.

### Additional Resources 📚
CISA provides several products detailing cyber defense best practices, including:
- **Improving Industrial Control Systems Cybersecurity with Defense-in-Depth Strategies**
- **ICS-TIP-12-146-01B--Targeted Cyber Intrusion Detection and Mitigation Strategies**

For the complete article, see: [Read full article](https://www.cisa.gov/news-events/ics-advisories/icsa-26-293-01)