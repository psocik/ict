---
title: GitHub - BushidoUK/Russian-APT-Tool-Matrix A Comprehensive Resource for Threat Hunting
date: 2026-08-13
categories: [CYBERSECURITY]
tags: [GITHUB,APT,RANSOMWARE,CYBERSECURITY,THREATHUNTING]
---

## New Resource Alert! 🚨

A new resource, titled **"A tool matrix for Russian APTs based on the Ransomware Tool Matrix,"** has been made available. This repository contains a list of which tools each Russian APT group uses. As defenders, we should exploit the fact that many of the tools used by these Russian APT groups are often reused. This allows us to threat hunt, deploy detections, and block these tools to eliminate the ability of adversaries to launch intrusions. This project will be updated as additional intelligence on Russian APT group TTPs is made available.

### Use Cases of the Russian APT Tool Matrix 📊
- **Threat Hunting:** A list of leads for threat hunting inside your environments.
- **Incident Response:** A checklist of tools to identify patterns of behavior between certain Russian APTs.
- **Adversary Emulation:** A resource for threat intelligence-led purple team engagements.

The matrix covers various tool categories, including:
- RMM Tools
- Exfiltration Tools
- Credential Theft Tools
- Defense Evasion Tools
- Networking Tools
- Discovery Tools
- Offensive Security Tools
- Living-off-the-Land Binaries and Scripts

This repository also contains multiple types of Russian APTs, including the GRU, SVR, and FSB. The alias of each Russian APT group has been chosen based on what the author believes it is most well-known as.

### Challenges Ahead ⚠️
Using the Russian APT Tool Matrix comes with its own challenges. While it is undoubtedly useful to have a list of tools commonly used by Russian APTs to hunt, detect, and block, there are some risks. Many of the tools referenced in this repository may be currently used by your IT team or even your Cybersecurity team. When hunting for these tools, you may uncover many installations of them inside your environment. Deciphering whether a tool is being used legitimately is difficult in a large or global environment. If you create a detection rule, you may generate a large number of alerts, which may get ignored or turned off without investigation. Moreover, if you block these tools without investigating legitimate usage, you may cause disruption to business operations and potentially impose costs on your organization.

For more details, check out the full article here: [Read full article](https://github.com/BushidoUK/Russian-APT-Tool-Matrix)