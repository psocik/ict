---
title: Over 390 Abandoned iCalendar Sync Domains Could Expose ~4 Million Devices to Security Risks
date: 2025-11-27
categories: [CYBER SECURITY]
tags: [SECURITY,ICALENDAR,DOMAINS]
---

If the domain hosting the calendar is abandoned and subsequently expires, it opens a dangerous vulnerability. Cybercriminals can re-register these expired domains, effectively hijacking the trust established by the original subscription. The attack vector is particularly insidious because it requires no new action from the victim. The user’s device continues to perform background synchronization requests to the now-malicious domain.

Bitsight security analysts identified this emerging threat landscape after investigating a single suspicious domain distributing holiday events. Their deep dive revealed a sprawling network of over 390 abandoned domains that were actively receiving synchronization requests. Further analysis indicated that these domains were communicating with approximately 4 million unique IP addresses daily, primarily from iOS and macOS devices.

The investigation uncovered specific technical patterns that facilitate this exploitation. The traffic is characterized by HTTP requests where the Accept header signals the device’s readiness to parse calendar files. The User-Agent string, typically containing the daemon identifier, explicitly identifies the source as the iOS Calendar system, confirming the request is a background process rather than a user-initiated browser visit.

Researchers categorized the malicious traffic into two main types: Base64-encoded URIs and Webcal query requests. The server responds with an iCalendar file that can contain manipulated event data. Additionally, the underlying infrastructure often employs heavily obfuscated JavaScript to execute deeper compromises.

To read the complete article see: [Cyber Security News](https://cybersecuritynews.com/over-390-abandoned-icalendar-sync-domains-could-expose/).