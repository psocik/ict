---
title: Tracking Updates to Raspberry Robin
date: 2025-08-04
categories: [RESEARCH]
tags: [MALWARE]
---

## Key Takeaways  
Raspberry Robin is an advanced malware downloader that has been active since 2021.  

The developers have improved the malware’s obfuscation methods by adding multiple initialization loops to functions with a flattened control flow, making brute-force decryption less efficient.  

The network encryption algorithm has changed from AES (CTR mode) to Chacha-20.  

Raspberry Robin has added a new local privilege escalation (LPE) exploit (CVE-2024-38196) to gain elevated privileges on targeted systems.  

The malware embeds invalid command-and-control (C2) server (TOR onion) domains.  

Certain values, such as the RC4 key seed, are randomized per sample/campaign.  

To read the complete article see:  
[Zscaler Blog](https://www.zscaler.com/blogs/security-research/tracking-updates-raspberry-robin)  
