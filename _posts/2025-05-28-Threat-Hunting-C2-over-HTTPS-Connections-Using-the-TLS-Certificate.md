---
title: Threat Hunting C2 over HTTPS Connections Using the TLS Certificate
date: 2025-05-28
categories: [RESEARCH]
tags: []
---

Introduction
As we’ve explored in numerous articles and Malware of the Day posts, there is no shortage of communication protocols threat actors can utilize for C2 communication. And while there is a whole smorgasbord of interesting and unusual protocols like IRC, FTP, ICMP, NTP etc. to choose from, these protocols are mostly confined to specific tasks and functions.

Thus despite the proliferation of new Open-Source projects using unusual protocols, or leveraging application APIs, the vast majority of C2 communication still relies on “the Big Three”: HTTP, HTTPS, and DNS.

Why these three? Well, a good C2 protocol needs two key things: it has to blend in with the traffic on the target network, and it has to be a plausible carrier of data. So choosing to merge in with the deluge of HTTP, HTTPS, or DNS packets is always a safe choice from the attacker’s POV.

And of these three, HTTPS takes the crown. The moment an attacker wraps their C2 communication in HTTPS, everything above the basic network layer (Layer 4) gets encrypted. Just like that, a whole slew of traditional network detection methods that peek into packet content are neutralized...

To read the complete article see:

[https://www.activecountermeasures.com/threat-hunting-c2-over-https-connections-using-the-tls-certificate/](https://www.activecountermeasures.com/threat-hunting-c2-over-https-connections-using-the-tls-certificate/)