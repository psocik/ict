---
title: Cybercriminals Abuse Open-Source Tools To Target Africa’s Financial Sector
date: 2025-06-24
categories: [SECURITY]
tags: [CYBERSECURITY,FINANCIAL SECTOR,AFRICA]
---

**Executive Summary**

Unit 42 researchers have been monitoring a series of attacks targeting financial organizations across Africa. We assess that the threat actor may be gaining initial access to these financial institutions and then selling it to others on the dark web. Since at least July 2023, a cluster of activity we track as CL-CRI-1014 has targeted this sector.

The attackers employ a consistent playbook, using a combination of open-source and publicly available tools to establish their attack framework. They also create tunnels for network communication and perform remote administration.

**These tools include:**
- **PoshC2:** An open-source attack framework  
- **Chisel:** An open-source tunneling utility  
- **Classroom Spy:** A remote administration tool  

The threat actor copies signatures from legitimate applications to forge file signatures, to disguise their tool set and mask their malicious activities. Threat actors often spoof legitimate products for malicious purposes. This does not imply a vulnerability in the organization’s products or services.

We suspect that the threat actors behind this activity are acting as an initial access broker. We assess their goal is to create footholds in financial institutions and sell this access on darknet markets. An initial access broker is a threat actor who specializes in gaining initial access to networks and selling that access to other threat actors.

To read the complete article see: [https://unit42.paloaltonetworks.com/cybercriminals-attack-financial-sector-across-africa/](https://unit42.paloaltonetworks.com/cybercriminals-attack-financial-sector-across-africa/).