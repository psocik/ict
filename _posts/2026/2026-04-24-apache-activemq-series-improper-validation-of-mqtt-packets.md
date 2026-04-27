---
title: Apache ActiveMQ Series Improper Validation of MQTT Packets
date: 2026-04-24
categories: [SECURITY]
tags: [APACHE,ACTIVEMQ,MQTT,VULNERABILITY]
---

## Apache ActiveMQ Vulnerability Report 🚨

The **Apache ActiveMQ series**, provided by The Apache Software Foundation, has been found to have an issue with the improper validation of MQTT packets. Specifically, the remaining length field of MQTT packets is not properly validated, which can lead to **integer overflow** and misinterpretation of the packets. This vulnerability is categorized as **Integer overflow or wraparound (CWE-190)**.

### Affected Products 📦
- Apache ActiveMQ 5.x versions prior to 5.19.2
- Apache ActiveMQ 6.x versions prior to 6.2.4
- Apache ActiveMQ All module 5.x versions prior to 5.19.2
- Apache ActiveMQ All module 6.x versions prior to 6.2.4
- Apache ActiveMQ MQTT module 5.x versions prior to 5.19.2
- Apache ActiveMQ MQTT module 6.x versions prior to 6.2.4

### Identified Vulnerabilities 🔍
- CVE-2025-66168
- CVE-2026-40046

### CVSS Scores 📊
- CVSS:4.0/AV:N/AC:L/AT:N/PR:L/UI:N/VC:L/VI:L/VA:N/SC:N/SI:N/SA:N Base Score 5.3
- CVSS:3.0/AV:N/AC:L/PR:L/UI:N/S:U/C:L/I:L/A:N Base Score 5.4

### Impact ⚠️
Processing a crafted MQTT packet may lead to misinterpretation and unexpected behavior. To mitigate this vulnerability, users are urged to update their software to the latest version as recommended by the developer.

This vulnerability was reported by **Gai Tanaka** of Mitsui Bussan Secure Directions, Inc. in version 6.2.0 to the developer and IPA under the Information Security Early Warning Partnership. **JPCERT/CC** coordinated with the developer to publish the advisory.

For more details, [Read full article](https://jvn.jp/en/jp/JVN20669184/)