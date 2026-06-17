---
title: Hidden in Teams DragonForce Attackers Weaponize Microsoft Teams Relays
date: 2026-06-16
categories: [CYBERSECURITY]
tags: [MALWARE,MICROSOFT TEAMS,CYBERSECURITY,DRAGONFORCE]
---

## Hidden in Teams: DragonForce Attackers Weaponize Microsoft Teams Relays

🚨 **Backdoor.Turn**, a Go-based RAT, is the first known malware to abuse Microsoft Teams' TURN relay servers to mask command-and-control traffic. Attackers deploying the DragonForce ransomware against a major U.S. services firm hid their command-and-control (C&C) traffic inside Microsoft Teams' own relay infrastructure, using a custom Go-based backdoor that Symantec is tracking as Backdoor.Turn. To network defenders, the only traffic they could see was outbound connections to legitimate Microsoft Teams servers. The attackers were on the victim network for between one and two months, with activity beginning in December 2025. Additionally, the attackers also used a previously unknown vulnerability in a Huawei driver.

### Key Features of Backdoor.Turn
- **Stealth Injection**: Backdoor.Turn is injected into the legitimate DbgView64.exe process for stealth.
- **Anonymous Access**: It obtains an anonymous Teams visitor token from Microsoft's Skype-backed identity services.
- **C&C Communication**: Uses a legitimate Microsoft TURN relay to set up the connection and runs a QUIC session to the attacker's real command-and-control (C2) server.

This is the first time TURN relay infrastructure has been abused this way in the wild. This mechanism is inspired by the Ghost Calls technique, presented at Black Hat in 2025, which focuses on super stealthy C&C communication difficult for network defenses to profile.

### Attackers' Strategies
The attackers utilized a sophisticated Bring Your Own Vulnerable Driver (BYOVD) strategy for defense evasion. They exploited known vulnerabilities in legitimate, signed drivers to gain kernel-level access, which was then used to terminate security processes. Key examples observed include:
- A novel "Havoc Process Terminator," leveraging Huawei's HWAuidoOs2Ec.sys.
- Exploits including CVE-2023-52271 for Topaz Antifraud's wsftprm.sys, CVE-2025-61155 for Tower of Fantasy's Gamedriverx64.sys, and CVE-2025-1055 for K7 Security Anti-Malware's K7RKScan.sys.
- The Abyss Worker driver, a custom-built malicious driver masquerading as a legitimate Palo Alto driver.

The attackers in this campaign use exceptionally sophisticated cyber tradecraft.

[Read full article](https://symantec-enterprise-blogs.security.com/threat-intelligence/dragonforce-msteams-backdoor)