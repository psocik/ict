---
title: Unverified COTS hardware enables persistent attacks in small satellites via SpyChain
date: 2025-10-14
categories: [RESEARCH]
tags: [COTS,SATELLITES,SPYCHAIN,SECURITY]
---

The paper introduces SpyChain, a framework for studying supply chain threats in small satellite systems. Unlike prior work focused on direct software attacks, SpyChain examines risks from third-party COTS hardware that often lacks strong verification but has deep system access. Using NASA’s NOS3 simulator, it demonstrates the first practical, persistent, multi-component supply chain attack on small satellites.

SpyChain tests five levels of attacks, from simple time-triggered components to complex, coordinated malware using multiple modules. In advanced cases, infected parts communicate through normal system messages or hidden file channels to launch attacks at key mission moments, such as after reaching orbit. The study shows these threats can remain stealth during testing and launch, activating only when certain conditions are met, making them very hard to spot before or after deployment.

The adversary model assumes a supply-chain insider or nation-state actor who embeds malware before launch and knows the flight-software interfaces (e.g., cFS, POSIX-like OS). With modest ground resources, access to a ground station or inexpensive software-defined radios, attackers can receive stolen data and control payloads. The researchers demonstrate that attackers can mount persistent, multi-phase campaigns that trigger only under mission-relevant conditions (e.g., orbital insertion), bypassing common architectural assumptions about module trust and component isolation, and making detection extremely difficult both pre-launch and in orbit.

The paper details SpyChain’s full attack lifecycle: supply-chain compromise, dormancy, telemetry- or event-triggered activation, covert exfiltration, and flexible actions from surveillance to sabotage. Coordinated multi-module malware is a new TTP in the SPARTA cyber kill chain. The study exposes major small sat vulnerabilities like weak runtime monitoring, no software bus authentication, poor access controls, and limited logging, highlighting the urgent risk of covert, persistent compromise amid growing space ransomware, espionage, and supply-chain threats.

[Read the complete article here](https://securityaffairs.com/183303/hacking/unverified-cots-hardware-enables-persistent-attacks-in-small-satellites-via-spychain.html)