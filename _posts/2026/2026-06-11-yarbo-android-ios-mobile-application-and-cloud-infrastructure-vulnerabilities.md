---
title: Yarbo Android/iOS Mobile Application and Cloud Infrastructure Vulnerabilities
date: 2026-06-11
categories: [SECURITY]
tags: [YARBO,MOBILE,VULNERABILITIES,CLOUD,SECURITY]
---

## Yarbo Android/iOS Mobile Application and Cloud Infrastructure Vulnerabilities 🚨

The recent vulnerabilities discovered in the Yarbo Android/iOS mobile applications and cloud infrastructure pose significant risks. Successful exploitation of these vulnerabilities could allow an attacker to obtain hard-coded credentials, gain access to telemetry data, and potentially send operational commands to the robot fleet. These issues affect Yarbo Android/iOS mobile applications versions below 3.17.4 and the Yarbo Cloud MQTT infrastructure (vers:all/*). The vulnerabilities have a global impact, affecting critical infrastructure sectors worldwide.

### Key Vulnerabilities:
- **CVE-2026-10557**: The Yarbo Android and iOS applications contain hard-coded MQTT broker credentials that are identical for all users and devices. These credentials are embedded in the application binary and can be easily extracted via APK decompilation.
- **CVE-2026-7368**: The Yarbo cloud does not enforce per-device or per-user authorization. Any client with valid credentials can subscribe to wildcard topics covering all robots globally and publish to any robot's command topic using only the robot's serial number.

Yarbo recommends users update the Yarbo mobile app to version 3.17.4 or later. Server-side broker authorization will be enforced automatically upon deployment of the May 2026 update, requiring no user action for this server-side change. These vulnerabilities, including CWE-798 (Use of Hard-coded Credentials) and CWE-862 (Missing Authorization), were reported to CISA by Markus Lassfolk of Truesec. As of the initial release date of June 11, 2026, no known public exploitation specifically targeting these vulnerabilities has been reported to CISA.

For more details, check the full article here: [Read full article](https://www.cisa.gov/news-events/ics-advisories/icsa-26-162-01)