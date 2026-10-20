---
title: PSA Patch Your Plex Media Server Before Someone Hacks It
date: 2026-10-19
categories: [SECURITY]
tags: [PLEX,VULNERABILITIES,MALWARE,SECURITY,CRYPTOMINER]
---

## PSA: Patch Your Plex Media Server Before Someone Hacks It 🚨

Recently fixed vulnerabilities in the Plex Media Server are under active exploitation in attacks that, when successful, install malware, including cryptominers and residential proxy apps, a researcher said. Plex fixed four vulnerabilities at the start of last month. However, three weeks later, published CVE designations revealed five vulnerabilities, with one of them carrying a severity rating of **8.6 out of 10**. A researcher last week revealed an exploit that chained four of them together to achieve remote code execution of the device running a vulnerable Plex version. This researcher subsequently named the chain **"Plex2Shell."**

Subsequently, these new details allowed a separate researcher to create a honeypot designed to track attempts in the wild to exploit the vulnerability chain. Within a day, this researcher began seeing active scanning of the simulated Plex server and eventually successful attempts to infect devices. So far, successful attacks are installing two distinct payloads. One such payload is a **cryptominer**, which uses the device to mine cryptocurrency and deposit it into a wallet controlled by the attacker. The other identified payload is **residential proxy software**, which allows people to anonymize their Internet activity (much of it illegal) by connecting to the infected box and then using it to send the user's traffic to a final destination.

The second researcher highlighted significant implications, writing: "Plex may be hosted on residential IP [sic] and I think threat actors would love to have residential IP proxy to access corporate VPNs and emails."

[Read full article](https://arstechnica.com/security/2026/10/recently-fixed-plex-media-vulnerabilities-are-being-exploited-to-install-malware/)\n