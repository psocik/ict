---
title: Bransys ELD Vulnerabilities Identified
date: 2026-09-17
categories: [CYBERSECURITY]
tags: [BRANSYS,VULNERABILITIES,CYBERSECURITY,CISA]
---

## Bransys ELD Vulnerabilities Identified

🚨 **Attention Users!** Successful exploitation of vulnerabilities in the Bransys ELD could allow unauthorized access to telemetry data and firmware. The Bransys ELD, deployed in Critical Infrastructure Transportation Systems within the United States, is affected. The following versions are impacted: **Android < 11.00.00** and **iOS < 1.1.54**.

### Identified Vulnerabilities
1. **CVE-2026-86520**: This vulnerability involves the product being shipped with hardcoded MQTT credentials, granting read access to real-time data for every active device connected to the affected MQTT broker. This falls under **CWE-798: Use of Hard-coded Credentials**.
2. **CVE-2026-77960**: Similar to the first, this stems from hardcoded FTP credentials, allowing an attacker to connect to the server and read data, also categorized under **CWE-798**.
3. **CVE-2026-86689**: This indicates susceptibility to cleartext transmission of sensitive information, allowing an attacker to connect to the broker and read all data, categorized as **CWE-319: Cleartext Transmission of Sensitive Information**.

### Recommendations
Bransys recommends that users update their systems through the app store:
- **Android users**: Update to version **11.00.00** or newer.
- **iOS users**: Update to version **1.1.54** or newer.

CISA advises users to take defensive measures to minimize the risk of exploitation:
- Minimize network exposure for all control system devices and systems.
- Ensure they are not accessible from the internet.
- When remote access is required, use secure methods like **Virtual Private Networks (VPNs)**.

No known public exploitation specifically targeting these vulnerabilities has been reported to CISA at this time. Jaime Lightfoot reported these vulnerabilities to CISA.

For more details, [Read full article](https://www.cisa.gov/news-events/ics-advisories/icsa-26-260-01).