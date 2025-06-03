---
title: GhostSpy Web-Based Android RAT  Advanced Persistent RAT with Stealthy Remote Control and Uninstall Resistance
date: 2025-05-21
categories: [MOBILE]
tags: []
---

At CYFIRMA, we are committed to delivering timely intelligence on emerging threats and attacker tactics. In this report, we analyze a high-risk Android malware variant that leverages advanced evasion, persistence, and surveillance techniques to achieve full control over infected devices.

The infection begins with a dropper that silently escalates privileges by exploiting Accessibility Services and UI automation to sideload and install a secondary APK (update.apk). Furthermore, the malware automatically grants itself all required permissions, simulating user interactions to bypass permission dialogs – eliminating the need for human interaction.

The main payload provides comprehensive control over the device, enabling keylogging, screen capture, background audio and video recording, SMS and call log theft, GPS location tracking, and remote command execution. It abuses Device Admin APIs to entrench itself deeply in the system and employs anti-uninstall tactics, including system dialog hijacking and full-screen overlay obfuscation, making it extremely persistent and nearly impossible to remove through conventional means.

Critically, the malware also bypasses banking app screen-mirroring protection using a skeleton view reconstruction method, which harvests the full UI layout of protected applications. This allows attackers to extract sensitive data from interfaces that typically block screenshots or screen sharing.

To read the complete article see:
[GhostSpy Web-Based Android RAT](https://www.cyfirma.com/research/ghostspy-web-based-android-rat-advanced-persistent-rat-with-stealthy-remote-control-and-uninstall-resistance/) 

**For more information, visit:** [Team Cymru Careers](https://www.team-cymru.com/careers)