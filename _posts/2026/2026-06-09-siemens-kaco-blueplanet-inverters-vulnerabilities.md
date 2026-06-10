---
title: Siemens KACO Blueplanet Inverters Vulnerabilities
date: 2026-06-09
categories: [CYBERSECURITY]
tags: [SIEMENS,VULNERABILITIES,INVERTERS,CYBERSECURITY,CISA]
---

## Siemens KACO Blueplanet Inverters Vulnerabilities

**Attention!** 🚨 KACO Blueplanet Inverters have been found to contain multiple vulnerabilities that could allow attackers to derive credentials from the device's serial number, leading to unauthorized access. KACO new energy GmbH has released updates for several affected products and strongly recommends upgrading to the latest versions. 

### Key Vulnerabilities:
- **CVE-2025-40946**: A critical flaw involving a CRC16-based algorithm for generating Technical Service credentials. This vulnerability allows attackers to misuse credentials derived from the device's serial number. The relevant CWE is **CWE-321** (Use of Hard-coded Cryptographic Key).
- **CVE-2026-41125**: An SQL injection vulnerability in the KACO Meteor server that allows an authorized attacker to elevate privileges over a local network. This is categorized under **CWE-89**.

### Recommendations:
- For affected products like blueplanet 100 TL3 GEN2 and blueplanet gridsafe 110 TL3-S, it is crucial to update to version V6.1.4.9 or later, or V3.91 or later, respectively. 
- Siemens strongly advises applying the provided security updates and protecting network access with appropriate mechanisms such as firewalls and VPNs.

### Additional Measures:
CISA recommends minimizing network exposure for all control system devices and ensuring they are not accessible from the internet. When remote access is necessary, utilize secure methods like VPNs, while being aware of potential vulnerabilities.

For more detailed information, please refer to the advisory released on **2026-05-12**. 

[Read full article](https://www.cisa.gov/news-events/ics-advisories/icsa-26-160-02) 
