---
title: Mirax Android Trojan Turns Devices Into Residential Proxy Nodes
date: 2026-04-13
categories: [CYBERSECURITY]
tags: [ANDROID,MALWARE,CYBERSECURITY,TROJAN]
---

## Mirax Android Trojan Turns Devices Into Residential Proxy Nodes 🚨

A newly identified Android banking trojan, known as **Mirax**, is spreading across Europe and combines remote access features with residential proxy capabilities to broaden its impact. According to an advisory published by Cleafy, the malware has been observed targeting Spanish-speaking users, with campaigns reaching more than **200,000 accounts** through advertisements on social media platforms.

Cleafy said Mirax represents a shift in how Android malware is developed and deployed. Unlike conventional threats, it operates under a restricted **Malware-as-a-Service (MaaS)** model, limiting access to a small group of affiliates. This controlled approach appears intended to maintain operational security while improving campaign effectiveness.

The malware enables attackers to fully control infected devices in real time. It can execute commands, monitor activity, and deploy fake overlays on legitimate applications to steal sensitive data. These overlays are fetched dynamically from command-and-control (C2) servers, complicating detection efforts. Mirax also integrates surveillance capabilities, including continuous keylogging and collection of lock screen details such as PIN structure and biometric usage. This allows attackers to gather credentials and personal information without raising suspicion.

The campaigns rely on **social engineering** to reach victims at scale. Malicious advertisements promote illegal streaming applications, encouraging users to download software from outside official app stores. Key elements of the distribution chain include:
- Social media advertisements used to reach large audiences
- Fake IPTV or streaming apps acting as droppers
- Malware hosted on GitHub with frequent updates
- Device checks designed to evade automated analysis

Once installed, the malware executes a multi-stage process, decrypting hidden payloads and establishing communication channels via **WebSockets**. These channels enable attackers to remotely control devices and extract data.

One of Mirax's defining features is its ability to convert infected devices into **residential proxy nodes**. This allows attackers to route malicious traffic through legitimate IP addresses, helping them bypass geographic restrictions and fraud detection systems. This functionality extends the malware's role beyond financial theft. Compromised devices can be used as infrastructure for broader cyber-criminal activity, including account takeovers (ATO) and anonymized network attacks.

Cleafy said Mirax reflects a wider evolution in mobile threats, where tools are becoming more modular and commercially structured. Although current campaigns focus on Spain, the analysts warned that the malware's reach is likely to expand as operators refine their tactics.

[Read full article](https://www.infosecurity-magazine.com/news/mirax-trojan-devices-proxy-nodes/)