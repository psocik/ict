---
title: GoldMelody’s Hidden Chords Initial Access Broker In-Memory IIS Modules Revealed
date: 2025-07-08
categories: [APT]
tags: [UNIT 42,GOLD MELODY,TGR-CRI-0045]
---

Unit 42 researchers uncovered a campaign by an initial access broker (IAB) to exploit leaked Machine Keys — cryptographic keys used on ASP.NET sites — to gain access to targeted organizations. IABs breach organizations and then sell that access to other threat actors.

This report analyzes the tools used in these attacks. We track this actor as the temporary group TGR-CRI-0045. The group seems to follow an opportunistic approach but has attacked organizations in Europe and the U.S. in the following industries: financial services, manufacturing, wholesale and retail, high technology, and transportation and logistics.

The IAB used these leaked keys to sign malicious payloads that provide unauthorized access to targeted servers, in a technique called ASP.NET View State deserialization. This technique enabled the IAB to execute malicious payloads directly in server memory, minimizing their on-disk presence and leaving few forensic artifacts, making detection more challenging.

We attribute the temporary group TGR-CRI-0045, with medium confidence, to Gold Melody (aka UNC961, Prophet Spider). This assessment is based on overlaps in the following:

- Indicators of compromise (IoCs)
- Tactics, techniques and procedures (TTPs)
- Victimology

This report also analyzes TGR-CRI-0045's infrastructure, as well as the tooling it used to gather information about other systems on the network and maintain access to the exploited systems. The tooling appears to be under active development.

To read the complete article see:

[GoldMelody’s Hidden Chords](https://unit42.paloaltonetworks.com/initial-access-broker-exploits-leaked-machine-keys/) 