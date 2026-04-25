---
title: GreyNoise Identifies New Scraper Botnet Concentrated in Taiwan
date: 2025-07-09
categories: [MALWARE]
tags: [GREYNOISE,SCRAPER BOTNET,TAIWAN]
---

GreyNoise has identified a previously untracked variant of a scraper botnet, detectable through a globally unique network fingerprint. While the botnet uses a simple and easily spoofed user-agent string — Hello-World/1.0 — its real signature lies in the behavior of the devices sending the traffic.

To detect it, GreyNoise analysts created a signature using JA4+, the suite of JA4 signatures used to fingerprint network traffic. This approach allows analysts to detect traffic based not on what it claims to be, but how it behaves — making it difficult to evade or spoof.

The signature includes:

- **JA4H (HTTP fingerprint)**: Captures how HTTP headers are ordered and formatted.
- **JA4T (TCP fingerprint)**: Encodes how a device establishes network connections.

These behavioral fingerprints form a meta-signature that is globally unique to this botnet variant.

[Read the complete article here](https://www.greynoise.io/blog/new-scraper-botnet-concentrated-in-taiwan).