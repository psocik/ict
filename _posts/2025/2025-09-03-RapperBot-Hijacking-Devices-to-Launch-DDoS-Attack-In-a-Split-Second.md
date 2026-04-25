---
title: RapperBot Hijacking Devices to Launch DDoS Attack In a Split Second
date: 2025-09-03
categories: [MALWARE]
tags: [DDOS,RAPPERBOT,CYBERSECURITY]
---

Bitsight analysts identified this activity as the work of a novel botnet they dubbed RapperBot, noting its unusually rapid kill chain and innovative use of legacy hardware constraints to evade detection.

Despite its potency, the malware’s behavior is elegantly simple: it mounts a remote NFS share to fetch and execute architecture-specific binaries, then self-deletes to run entirely in memory.

RapperBot’s infection vector capitalizes on the administrative port (TCP 34567) of vulnerable NVRs. Upon identifying an exposed device, the attacker exploits a path traversal flaw to download account configuration files, revealing both hashed and plaintext credentials. With these credentials, the attacker initiates a fake firmware update, sending a ZIP-formatted payload over the proprietary update protocol.

To read the complete article see:
[Cybersecurity News](https://cybersecuritynews.com/rapperbot-hijacking-devices/)  
😮