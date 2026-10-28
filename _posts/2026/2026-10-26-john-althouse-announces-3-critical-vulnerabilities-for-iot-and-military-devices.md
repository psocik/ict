---
title: John Althouse Announces 3 Critical Vulnerabilities for IoT and Military Devices
date: 2026-10-26
categories: [SECURITY]
tags: [VULNERABILITIES,IOT,MILITARY,SECURITY,PATCHES]
---

## John Althouse on X - Announcing 3 Critical Vulnerabilities 🚨

John Althouse has revealed **3 critical vulnerabilities** affecting hundreds of millions of IoT devices, firewalls, operational technology (OT), and military devices. This includes major brands like **Palo Alto Networks, Comcast, D-Link, HP, Canon, Honeywell, GE, Oracle, Siemens, Rockwell, Digi, Lockheed Martin,** and **Boeing**. 

The vulnerabilities are associated with the **GoAhead Web Server**, a backend library utilized by these devices. While a patch is available from GoAhead, it does not guarantee that device manufacturers will implement it. 

### Key Issues:
- **TLS Traffic Vulnerability:** 
  - TLS traffic over DHE ciphers has a 1-byte secret, "04". This flaw allows anyone to decrypt connections to these devices, potentially stealing login credentials and session tokens, especially if clients negotiate with DHE ciphers like **TLS_DHE_RSA_WITH_CHACHA20_POLY1305_SHA256**.

- **mTLS Bypass:** 
  - The **LibreSSL mTLS** has been completely bypassed, allowing unauthorized connections over mTLS. If you have devices exposed to the internet relying on mTLS for protection, it is crucial to take them offline or apply patches immediately.

- **OpenSSL Certificate Revocation Lists:** 
  - CRLs are not enforced, meaning if a user device is compromised and its mTLS certificate is revoked, the revocation has no effect. This opens up numerous attack vectors.

These vulnerabilities are critical as they impact essential services that run our world, including **water systems, electricity, military operations, firewalls,** and other critical infrastructure.

For more details, read the full article here: [Read full article](https://x.com/4A4133/status/2114822201555943763) 
