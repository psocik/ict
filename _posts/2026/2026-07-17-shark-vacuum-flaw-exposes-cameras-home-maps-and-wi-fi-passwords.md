---
title: Shark Vacuum Flaw Exposes Cameras, Home Maps and Wi-Fi Passwords
date: 2026-07-17
categories: [SECURITY]
tags: [SHARK,VACUUM,SECURITY,IOT]
---

## Shark Vacuum Flaw Exposes Cameras, Home Maps and Wi-Fi Passwords 🚨

Shark's cloud-connected robot vacuums are currently exposed by an unpatched AWS (Amazon Web Services) IoT (Internet of Things) policy flaw. This vulnerability could turn one compromised device into a remote-control skeleton key for many others in the same region, granting access to cameras, maps, and Wi-Fi passwords.

A researcher using the handle **tokay0** disassembled a Shark RV2320EDUS robot vacuum and discovered that its embedded AWS IoT certificate is permitted to publish and subscribe to topics for any Shark device in the same AWS Region, not just its own. By design, AWS provides per-device "shadows" that store state such as configuration and commands. However, Shark's overly permissive Message Queuing Telemetry Transport (MQTT) policy allows a stolen certificate to communicate with other vacuums' shadows as well.

While the certificate was extracted from the vacuum using physical access and a debug console, the subsequent abuse is remote and cloud-based. According to the researcher, an attacker with cloud access could:
- Watch from the vacuum's camera, turning it into a mobile surveillance device inside your home.
- Steal the Wi-Fi password, which is stored in plaintext, potentially giving them a foothold on your local network.
- Copy the vacuum's map of your house, revealing room layouts and how frequently different areas are used.

Using the certificate from his own vacuum, the researcher monitored traffic from Shark devices in the same AWS Region and determined which ones supported remote command execution. During a 24-hour period in a single AWS Region, the researcher observed **1,517,605 unique Shark serial numbers** and found that **673,816 devices** (about 44%) responded in a way that indicated support for the remote command execution feature.

The core issue is a cloud-side policy that is not strict enough, making this a server-side problem rather than a firmware bug you can patch yourself. Despite being notified more than six months ago, SharkNinja has not fixed the vulnerability. Until that changes, owners should:
- Put pressure on Shark to fix the issue.
- Disable remote control for the vacuum or disconnect it from Wi-Fi if you do not need its smart features.
- Watch for announcements from Shark about a fix, CVE, or recall.

For more details, [Read full article](https://www.malwarebytes.com/blog/news/2026/07/shark-vacuum-flaw-exposes-cameras-home-maps-and-wi-fi-passwords).