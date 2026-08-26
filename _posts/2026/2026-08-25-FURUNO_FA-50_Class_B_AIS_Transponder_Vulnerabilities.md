---
title: FURUNO FA-50 Class B AIS Transponder Vulnerabilities
date: 2026-08-25
categories: [SECURITY]
tags: [FURUNO,AIS,VULNERABILITIES,SECURITY,TRANSPORTATION]
---

## FURUNO FA-50 Class B AIS Transponder Vulnerabilities

🚨 **Critical Alert!** Successful exploitation of these vulnerabilities could allow an attacker to alter device settings. The following versions of the FURUNO FA-50 Class B AIS Transponder are affected: **vers:all/**. These vulnerabilities impact **Critical Infrastructure Sectors**, specifically **Transportation Systems**, and are deployed **Worldwide**.

### Vulnerability Details

- **CVE-2026-59769**: An attacker with knowledge of credentials and access to the in-vessel network may operate the settings screen to alter device settings. This vulnerability is categorized as **CWE-798**, "Use of Hard-coded Credentials."
- **CVE-2026-67578**: Allows some configurations to be changed on the management screen without authentication, categorized as **CWE-306**, "Missing Authentication for Critical Function."

### Recommendations

FURUNO ELECTRIC CO., LTD. notes that production of this product ended in **October 2020**, and software updates will no longer be provided. To prevent unauthorized access, it is recommended that users do not connect the product directly to the internet. Ensure the vessel on which the product is installed is properly locked and managed. CISA also recommends taking defensive measures to minimize the risk of exploitation:

- Minimize network exposure for all control system devices.
- Ensure devices are not accessible from the internet.
- Locate control system networks behind firewalls and isolate them from business networks.
- Use secure methods like **VPNs** for remote access, while recognizing that VPNs may have vulnerabilities and should be updated regularly.

### Reporting and Monitoring

Organizations observing suspected malicious activity should follow established internal procedures and report findings to CISA for tracking and correlation against other incidents.

These vulnerabilities were reported to CISA by **Souvik Kandar**, with JPCERT/CC coordinating with Furuno Electric and CISA. No known public exploitation specifically targeting these vulnerabilities has been reported to CISA at this time.

For more information, [Read full article](https://www.cisa.gov/news-events/ics-advisories/icsa-26-237-07).