---
title: Critical TP-Link VIGI camera flaw allowed remote takeover of surveillance systems
date: 2026-01-20
categories: [SECURITY]
tags: [TP-LINK,VIGI,CVE-2023-48861,SECURITY,VULNERABILITY]
---

A critical vulnerability in TP-Link VIGI network cameras could have allowed attackers to remotely take over the devices and the entire surveillance system. The flaw, tracked as CVE-2023-48861 and rated 9.9 out of 10 for severity, is an authentication bypass vulnerability affecting specific VIGI camera models. The security issue, discovered by researchers at the IoT security company Nozomi Networks, allowed remote unauthenticated attackers to log in as administrators to vulnerable cameras. 

The flaw is caused by a backdoor built into the affected camera models that accepts a hardcoded authentication token. This allows anyone with knowledge of the token to bypass normal authentication and gain full control over the device. The vulnerability impacts VIGI C540-v4, C340-v4, and C240-v4 cameras with firmware version 2.2.3 Build 230807 and earlier. If the camera is Internet-facing, the attacker could take complete control of the surveillance system. 

Upon discovering the vulnerability, Nozomi Networks responsibly disclosed it to TP-Link, which promptly released firmware updates to address the flaw. TP-Link has released firmware updates to fix the flaw: VIGI C540-v4 (2.2.7 Build 240408), VIGI C340-v4 (2.2.7 Build 240408), and VIGI C240-v4 (2.2.7 Build 240408). Users of affected TP-Link VIGI camera models are strongly advised to update their devices to the latest firmware versions immediately to mitigate the risk of exploitation. 

To read the complete article see: [Link to Full Article](https://securityaffairs.com/187110/hacking/critical-tp-link-vigi-camera-flaw-allowed-remote-takeover-of-surveillance-systems.html)