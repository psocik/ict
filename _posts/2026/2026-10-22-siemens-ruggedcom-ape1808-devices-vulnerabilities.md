---
title: Siemens RUGGEDCOM APE1808 Devices Vulnerabilities
date: 2026-10-22
categories: [CYBERSECURITY]
tags: [SIEMENS,RUGGEDCOM,VULNERABILITIES,CYBERSECURITY,CISA]
---

## Siemens RUGGEDCOM APE1808 Devices Vulnerabilities

Nozomi Networks has published critical information regarding vulnerabilities in **Nozomi Guardian/CMC** affecting various Siemens Industrial products. The following versions of Siemens RUGGEDCOM APE1808 Devices are impacted: RUGGEDCOM APE1808 vers:all/* (CVE-2026-33387, CVE-2026-33388, CVE-2026-33389, CVE-2026-33391, CVE-2026-33920). These devices are deployed globally across **Critical Infrastructure Sectors** such as:
- Critical Manufacturing
- Transportation Systems
- Energy
- Healthcare and Public Health
- Financial Services
- Government Services and Facilities

Siemens ProductCERT has reported these vulnerabilities to CISA.

### Vulnerabilities Overview

1. **CVE-2026-33387**: A template injection vulnerability in the Dashboards functionality due to improper validation of an input parameter. An authenticated user can define a dashboard containing a malicious payload, which executes in the victim's browser context, allowing attackers to modify application data or disrupt availability.

2. **CVE-2026-33389**: An improper certificate/host key validation vulnerability in the Smart Polling functionality, allowing a man-in-the-middle attacker to intercept communications and capture credentials.

3. **CVE-2026-33388**: Access control vulnerability in the Credentials Manager, enabling a remote authenticated user to view and manipulate entries, potentially disrupting authentication for dependent devices.

4. **CVE-2026-33391**: Insufficient validation of user privileges allows an authenticated user to bypass access controls and modify Smart Polling configurations.

5. **CVE-2026-33920**: A cross-site request forgery vulnerability in the login functionality due to missing validation of the anti-CSRF token, compromising the integrity of the audit trail.

### Recommendations

For remediation, Siemens recommends contacting customer support for patch and update information. CISA advises users to take defensive measures to minimize the risk of exploitation, including:
- Minimizing network exposure for all control system devices.
- Ensuring devices are not accessible from the internet.
- Isolating control system networks behind firewalls.
- Using secure remote access methods, such as **VPNs**.

Siemens strongly recommends protecting network access to devices with appropriate mechanisms and configuring the environment according to Siemens' operational guidelines for **Industrial Security**. CISA encourages organizations to implement recommended cybersecurity strategies for proactive defense of ICS assets.

For more details, you can read the complete article here: [Read full article](https://www.cisa.gov/index.php/news-events/ics-advisories/icsa-26-295-18) 
