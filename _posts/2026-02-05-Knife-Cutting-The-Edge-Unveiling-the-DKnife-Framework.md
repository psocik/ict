---
title: Knife Cutting The Edge Unveiling the DKnife Framework
date: 2026-02-05
categories: [RESEARCH]
tags: [CYBERSECURITY,MALWARE,DKNIFE,CISCO,THREAT-ACTORS]
---

## Knife Cutting The Edge: Unveiling the DKnife Framework

**Cisco Talos** has uncovered a sophisticated framework known as **DKnife**, which is designed for gateway monitoring and adversary-in-the-middle (AitM) attacks. This framework includes seven Linux-based implants that perform deep packet inspection, manipulate traffic, and deliver malware through routers and edge devices. 

### Key Findings:
- **Active Since 2019**: DKnife has been operational since at least 2019, with command and control (C2) servers still active as of January 2026.
- **Targeted Devices**: The attacks target a wide range of devices, including PCs, mobile devices, and Internet of Things (IoT) devices.
- **Malware Delivery**: DKnife interacts with the **ShadowPad** and **DarkNimbus** backdoors by hijacking binary downloads and Android application updates.

### Language and Targeting:
DKnife primarily targets Chinese-speaking users, as indicated by credential harvesting for Chinese-language services and exfiltration modules for popular Chinese mobile applications. The code and configuration files contain references to Chinese media domains, suggesting that threat actors from China operate this tool.

### Connection to Other Campaigns:
Talos also discovered a link between DKnife and a campaign delivering **WizardNet**, a modular backdoor associated with another AitM framework, **Spellbinder**. This connection indicates a shared development or operational lineage between these frameworks.

For more detailed insights, read the complete article here: [Read full article](https://blog.talosintelligence.com/knife-cutting-the-edge/)