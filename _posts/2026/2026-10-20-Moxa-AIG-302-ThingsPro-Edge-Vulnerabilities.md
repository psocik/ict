---
title: Moxa AIG-302 ThingsPro Edge Vulnerabilities
date: 2026-10-20
categories: [CYBERSECURITY]
tags: [MOXA,VULNERABILITIES,CYBERSECURITY,CRITICAL-INFRASTRUCTURE]
---

## Moxa AIG-302 ThingsPro Edge Vulnerabilities 🚨

**Published on:** October 20, 2026  
**Source:** CISA  

Successful exploitation of these vulnerabilities could allow an attacker to obtain and disclose sensitive information. The Moxa AIG-302 ThingsPro Edge firmware **<=1.4.0** is affected by two critical vulnerabilities, **CVE-2026-109812** and **CVE-2026-109813**. These vulnerabilities impact Critical Infrastructure Sectors including Critical Manufacturing, Energy, and Water and Wastewater Systems, with deployments reported worldwide.

### Vulnerability Details:
- **CVE-2026-109812**: This describes a missing authorization vulnerability (CWE-862) in the internal API `/api/v1/secrets/` for some of Moxa's industrial computing products. A privileged authenticated attacker with adjacent network access could exploit this vulnerability to access sensitive information, potentially resulting in the disclosure of confidential data, including cryptographic key material.
- **CVE-2026-109813**: This covers a hard-coded cryptographic key vulnerability (CWE-321) in the `/usr/bin/sysman` for some of Moxa's industrial computing products. An unauthenticated attacker with adjacent network access could exploit the exposed private key material to compromise the confidentiality and integrity of communications.

### Recommended Actions:
Moxa has provided a fix for the vulnerability in **v1.4.1**. Users are encouraged to obtain and apply the update through one of the following methods:
- If the AIG-302 has Internet access, log in to the AIG-302 Web Console, go to **Maintenance > Software Upgrades**, and click **Check for upgrades** to check for and obtain the update.
- Users can also download the **v1.4.1** patch manually from either the official AIG-302 product website or the Moxa Software Release Service. Then, log in to the AIG-302 Web Console, navigate to **Maintenance > Software Upgrades**, and select **Package Upload** to upload the patch.

For more information, refer to Moxa's security advisory **MPSA-262560**. CISA recommends users take defensive measures to minimize the risk of exploitation of these vulnerabilities, including:
- Minimizing network exposure for all control system devices and/or systems.
- Ensuring they are not accessible from the internet.
- Locating control system networks and remote devices behind firewalls and isolating them from business networks.
- When remote access is required, using more secure methods, such as **Virtual Private Networks (VPNs)**.

No known public exploitation specifically targeting these vulnerabilities has been reported to CISA at this time. These vulnerabilities are not exploitable remotely.

[Read full article](https://www.cisa.gov/news-events/ics-advisories/icsa-26-293-03)