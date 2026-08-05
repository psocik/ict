---
title: Multiple Vulnerabilities in DEEBOT PRO M1, DEEBOT PRO K1VAC and ECOVACS PRO App
date: 2026-08-04
categories: [SECURITY]
tags: [VULNERABILITIES,ECOVACS,ROBOTICS,SECURITY]
---

## Multiple Vulnerabilities in DEEBOT PRO M1, DEEBOT PRO K1VAC and ECOVACS PRO App

Robotic cleaners **DEEBOT PRO M1** and **DEEBOT PRO K1VAC**, along with the mobile app **ECOVACS PRO App** developed by **ECOVACS ROBOTICS**, contain multiple vulnerabilities. These products are provided in Japan by **Hellohas Robotics Inc.**

### Affected Products
- DEEBOT PRO M1 prior to M1-1.7.27
- DEEBOT PRO K1VAC prior to V1.7.821
- Android/iOS App "ECOVACS PRO" prior to 1.3.82

### Key Vulnerabilities
1. **CVE-2026-66403**: A critical vulnerability due to a web server for debugging purposes remaining enabled (CWE-489), with a CVSS Base Score of 8.7. This could allow retrieval of floor map and log information stored on the product.
2. **CVE-2026-66405**: Involves a telnet server remaining enabled (CWE-489), with a CVSS Base Score of 8.8, which may allow unauthorized login to the affected product.
3. **CVE-2026-66406**: Arbitrary code execution may occur due to missing server certificate verification in the wget command.
4. **CVE-2026-66407**: Describes the use of a Broken or Risky Cryptographic Algorithm in WebSocket communication authentication (CWE-327), with a CVSS Base Score of 8.1. An attacker may alter communications through this vulnerability.
5. **CVE-2026-66411**: Incorrect implementation of the authentication algorithm in WebSocket communications (CWE-303) could allow an attacker to connect without authentication.

### Additional Issues
- Missing server certificate verification in MQTT communications (CVE-2026-66404)
- Weak passwords for the root account (CVE-2026-66408)
- Weak passwords for the Wi-Fi hotspot network (CVE-2026-66409)

### Response
According to **Hellohas Robotics Inc.**, all users have been notified and all affected products have been updated. They reported and coordinated these vulnerabilities with **ECOVACS ROBOTICS** and notified users of the solutions through **JPCERT/CC**.

For more details, you can read the complete article here: [Read full article](https://jvn.jp/en/vu/JVNVU92804348/)