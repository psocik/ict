---
title: ASUS Control Center Flaw Allows Attackers to Gain Full Admin Control
date: 2026-09-06
categories: [CYBERSECURITY]
tags: [ASUS,SECURITY,VULNERABILITY,ADMIN,CONTROL]
---

## ASUS Control Center Vulnerability Alert 🚨

ASUS has issued an urgent security update for **ASUS Control Center Enterprise (ACC)** after researchers uncovered a maximum-severity vulnerability that allows remote attackers to seize complete administrative control over the platform and every device it manages, without needing a password or any user interaction. 

Tracked as **CVE-2026-75754**, this flaw carries a **CVSS score of 10.0**, the highest possible rating, reflecting how easily it can be exploited over a network and the catastrophic scope of what an attacker can achieve once inside.

### How the Vulnerability Works 🔍
The vulnerability stems from a chain of three separate weaknesses:
- **Missing Authentication:** ASUS Control Center lacks authentication on a critical function, allowing sensitive operations to be triggered by anyone who can reach the service over the network.
- **Server-Side Request Forgery Flaw:** This lets an attacker send a specially crafted HTTP request to trick the system into exposing its own encryption key.
- **Hard-Coded Credentials:** ASUS Control Center contains hard-coded credentials baked into the software itself.

Once attackers obtain the encryption key, they can use these fixed credentials to log directly into the newly opened SSH port and gain a full root shell, the highest level of system access available on the machine. From there, intruders can read, modify, or delete any data stored in ACC, potentially compromising an entire corporate IT environment.

### Immediate Actions Required ⚠️
The flaw affects all versions of ASUS Control Center Enterprise up to and including 4.0.0.2. ASUS urges every organization running the software to update immediately to version 3.1.0.9 or later. Further fix details are posted on its official Security Advisory page. 

For enterprises unable to patch right away, it is advised to:
- Isolate ACC management interfaces from public networks.
- Block inbound and outbound traffic on port 2222.
- Audit hosts for unexpected SSH listeners as an interim safeguard.

For more information, [Read full article](https://cybersecuritynews.com/asus-control-center-vulnerability/).