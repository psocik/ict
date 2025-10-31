---
title: Threat Actors Utilize AdaptixC2 for Malicious Payload Delivery
date: 2025-10-30
categories: [TOOLS]
tags: [CYBERSECURITY,RANSOMWARE,ADAPTIXC2]
---

A surge in cybercriminal abuse of AdaptixC2, a free adversarial emulation framework created initially for penetration testers, has been detected in active ransomware operations.

AdaptixC2 operates as an extensible post-exploitation platform, with a Golang-based server and a GUI built in C++ and QT for cross-platform use.

A DFIR investigation found an Akira affiliate using the tool. Akira has breached more than 250 organizations and generated about 2m since 2023, targeting businesses and critical infrastructure in Europe, North America and Australia.

In their latest advisory, Silent Push shared a series of key indicators to watch to protect against this threat:
- Network traffic contacting infrastructure associated with AdaptixC2 servers;
- Signs of CountLoader activity, which may precede AdaptixC2 deployment;
- Unusual Golang-based command-and-control communications;
- Unknown C++ QT applications executing within Windows, macOS or Linux environments.

To read the complete article see: [Infosecurity Magazine](httpss://www.infosecurity-magazine.com/news/adaptixc2-malicious-payload/) 
