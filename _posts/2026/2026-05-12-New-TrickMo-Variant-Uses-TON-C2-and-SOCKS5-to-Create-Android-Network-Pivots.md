---
title: New TrickMo Variant Uses TON C2 and SOCKS5 to Create Android Network Pivots
date: 2026-05-12
categories: [CYBERSECURITY]
tags: [TRICKMO,MALWARE,ANDROID,CYBERSECURITY,BANKING]
---

## New TrickMo Variant Uses TON C2 and SOCKS5 to Create Android Network Pivots 🚨

Cybersecurity researchers have flagged a new version of the TrickMo Android banking trojan that uses The Open Network (TON) for command-and-control (C2). This new variant, observed by ThreatFabric between January and February 2026, actively targets banking and cryptocurrency wallet users in France, Italy, and Austria.

ThreatFabric stated that **TrickMo** relies on a runtime-loaded APK (dex.module), which has been updated with new features that add network-oriented functionality, including reconnaissance, SSH tunneling, and SOCKS5 proxying capabilities. This allows infected devices to function as programmable network pivots and traffic-exit nodes.

TrickMo has been active since late 2019 and was first flagged by CERT-Bund and IBM X-Force for its ability to abuse Android's accessibility services to hijack one-time passwords (OTPs).

The latest versions, labeled TrickMo C, are distributed via phishing websites and dropper apps. A notable shift in architecture includes the use of the TON decentralized blockchain for stealthy C2 communications. ThreatFabric detailed that **TrickMo** carries an embedded native TON proxy that the host APK starts on a loopback port at process start. The bot's HTTP client is wired through that proxy, ensuring every outbound command-and-control request is addressed to an .adnl hostname and resolved through the TON overlay.

Dropper apps containing the malware masquerade as adult-friendly versions of TikTok through Facebook, while the actual malware impersonates Google Play Services. Previous iterations of "dex.module" implemented accessibility-driven remote control functionality through a socket.io-based channel, but the new version utilizes a network-operative subsystem that supports commands like curl, dnslookup, ping, telnet, and traceroute. This gives attackers a remote shell-equivalent for network reconnaissance from the victim's network position, including any internal corporate or home network the device is currently associated with.

Another important feature is a **SOCKS5 proxy** that turns the compromised device into a network exit node, routing malicious traffic while defeating IP-based fraud-detection signatures on banking, e-commerce, and cryptocurrency exchange services. ThreatFabric concluded that instead of relying on conventional DNS and public internet infrastructure, the malware communicates through .adnl endpoints routed via an embedded local TON proxy, reducing the effectiveness of traditional takedown and network-blocking efforts while blending the traffic with legitimate TON activity. Furthermore, this latest variant expands the operational role of infected devices through SSH tunneling and authenticated SOCKS5 proxying, effectively turning compromised phones into programmable network pivots and traffic-exit nodes whose connections originate from the victim's own network environment. 

[Read full article](https://thehackernews.com/2026/05/new-trickmo-variant-uses-ton-c2-and.html)