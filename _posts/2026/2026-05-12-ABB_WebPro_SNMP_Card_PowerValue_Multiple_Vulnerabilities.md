---
title: ABB WebPro SNMP Card PowerValue Multiple Vulnerabilities
date: 2026-05-12
categories: [SECURITY]
tags: [ABB,VULNERABILITIES,SNMP,SECURITY]
---

## ABB WebPro SNMP Card PowerValue Multiple Vulnerabilities 🚨

ABB has identified multiple vulnerabilities in the WebPro SNMP card PowerValue for certain product versions. These vulnerabilities could allow an attacker with local network access to exploit the following issues:

- **Unauthorized Access**
- **Insufficient Session Expiration** leading to resource unavailability
- **Uncontrolled Resource Consumption** resulting in a Denial of Service (DoS) attack.

The affected versions include WebPro SNMP Card <=1.1.8.k, which are deployed globally across Critical Infrastructure Sectors. An attacker could exploit these vulnerabilities by sending specially crafted messages to the WebPro SNMP Card PowerValue device, requiring network access either directly or through a compromised security system.

### Vulnerability Details

1. **CVE-2025-4675**: The Modus (slave) protocol was incorrectly implemented, causing instability on port 502 and making the Modbus service unavailable until a manual reboot is performed (CWE-754 Improper Check for Unusual or Exceptional Conditions).
2. **CVE-2025-4676**: The device's web HMI authenticates users by validating the first character of the session cookie and authentication token. An attacker can easily brute-force this first character, allowing them to bypass the authentication (CWE-303 Incorrect Implementation of Authentication Algorithm).
3. **CVE-2025-4677**: Idle session timeout is not configured for ports 23 and 502, enabling an attacker to make numerous connections, leading to resource unavailability (CWE-613 Insufficient Session Expiration).

### Recommended Actions

ABB strongly advises customers to update to the latest firmware version 1.1.8.p to correct these vulnerabilities. Users of affected product versions should contact ABB Digital Service Support for guidance and recommended actions. If upgrading is not feasible, immediate application of mitigating factors as outlined in the "General security recommendations" is advised.

CISA recommends minimizing network exposure for all control system devices and ensuring they are not accessible from the internet. Control system networks and remote devices should be located behind firewalls and isolated from business networks. When remote access is necessary, more secure methods such as Virtual Private Networks (VPNs) should be used.

For more information, read the complete article here: [Read full article](https://www.cisa.gov/news-events/ics-advisories/icsa-26-132-06)