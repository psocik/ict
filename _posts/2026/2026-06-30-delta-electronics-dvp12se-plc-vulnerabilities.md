---
title: Delta Electronics DVP12SE PLC Vulnerabilities
date: 2026-06-30
categories: [CYBERSECURITY]
tags: [DELTA,VULNERABILITIES,CYBERSECURITY,PLC]
---

## Delta Electronics DVP12SE PLC Vulnerabilities 🚨

**Source:** CISA  
**Date Published:** June 30, 2026  

Successful exploitation of these vulnerabilities could allow an attacker to remotely issue commands, modify operational values, interfere with control logic, and alter device behavior without authentication or privilege enforcement. The following versions of Delta Electronics DVP12SE PLC are affected: DVP12SE PLC vers:all/* (CVE-2026-12819, CVE-2026-12818). These critical infrastructure vulnerabilities impact Critical Manufacturing sectors and are deployed worldwide. Adm Bin Harbi (0xnoag) from Corvo Security reported these vulnerabilities to CISA. The initial release date for this advisory is 2026-06-30.

### Vulnerability Details

- **CVE-2026-12819**: This vulnerability exposes a Modbus TCP service over a specified port without authentication or access control, permitting unauthenticated interaction with security-sensitive PLC functions. The device accepts Modbus commands from any reachable network source without requiring credentials, privilege validation, or operator approval, allowing unauthorized read and write access to coils, holding registers, operational memory, relay states, and process control functions. This vulnerability is classified under CWE-306 Missing Authentication for Critical Function.

- **CVE-2026-12818**: Indicates that Delta Electronics DVP12SE PLCs are susceptible to a resource allocation vulnerability without limits or throttling (CWE-770) within their Modbus TCP service. A remote attacker could exploit this vulnerability by flooding the Modbus port (TCP/502) with a continuous stream of raw network packets or specially crafted and malformed packets. This vulnerability is associated with CWE-770 Allocation of Resources Without Limits or Throttling.

### Recommended Actions

Delta Electronics is aware of these vulnerabilities and is currently working on a fix. They recommend users apply the following workarounds:

- Enable the IP Filter feature, configuring and enabling the PLC's built-in IP Filter function via the programming software. Restrict access exclusively to the IP addresses of trusted devices (such as designated HMI panels or SCADA hosts) to block unauthorized network access.
- Set up PLC password protection to ensure the device's core control logic and parameters cannot be easily downloaded, overwritten, or tampered with.
- Implement network isolation and firewall protection by deploying the PLC within an independent local area network (OT control network) secured by a firewall. Never connect the device directly to the office network or the Internet.
- If remote access is required, enforce the use of a secure, authorized VPN tunnel.

For more information, refer to Delta Electronic's advisory page at [Delta Advisory](https://www.deltaww.com/en-US/service-support/product-cybersecurity/advisory). CISA also recommends users take defensive measures to minimize the risk of exploitation of these vulnerabilities, including minimizing network exposure for all control system devices and/or systems, ensuring they are not accessible from the internet. Control system networks and remote devices should be located behind firewalls and isolated from business networks.

No known public exploitation specifically targeting these vulnerabilities has been reported to CISA at this time.

[Read full article](https://www.cisa.gov/news-events/ics-advisories/icsa-26-181-07)