---
title: Konfety Returns Classic Mobile Threat with New Evasion Techniques
date: 2025-07-15
categories: [MOBILE SECURITY]
tags: [MALWARE,MOBILE,SECURITY,EVASION TECHNIQUES]
---

As part of our ongoing mission to identify emerging threats to mobile security, our zLabs team has been actively tracking a new, sophisticated variant of a well-known malware previously reported by Human. This Android-targeted malware, named Konfety, employs an “evil-twin” method to conduct fraudulent activities. Notably, two distinct variants of this application share the same Package Name, a tactic designed to enhance its evasiveness and impact:

- **Dual-App Deception:** Uses the same package name for both a benign app (on official stores) and a malicious version distributed via third-party sources.
- **ZIP-Level Evasion:** Tampered APK structure (e.g., unsupported compression, fake encryption flags) breaks common analysis tools and complicates reverse engineering.
- **Dynamic Code Loading:** Conceals key functionality in encrypted assets that are only decrypted and executed at runtime.
- **Stealth Techniques:** Hides app icon, mimics legitimate apps, and applies geofencing to adjust behavior by region.
- **Ad Fraud Infrastructure:** Leverages CaramelAds SDK to fetch ads, deliver payloads, and maintain communication with attacker-controlled servers.
- **User Impact:** Redirects users to malicious websites, prompts unwanted app installs, and triggers persistent spam-like browser notifications.

To read the complete article see: [Zimperium](https://zimperium.com/blog/konfety-returns-classic-mobile-threat-with-new-evasion-techniques) 
