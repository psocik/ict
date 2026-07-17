---
title: Tracking Donot APT C 35 Bangladesh Military Intrusion
date: 2026-07-16
categories: [CYBERSECURITY]
tags: [BANGLADESH,CYBER-ESPIONAGE,MILITARY,APT-C-35]
---

## Tracking Donot APT C 35 Bangladesh Military Intrusion

A targeted cyber-espionage operation against Bangladesh's military and defense establishment has been identified. The initial access was achieved through a spear-phished RTF document disguised as the biography of a Bangladesh Air Force officer. This RTF pulls a malicious VBA macro via remote template injection, with server-side geofencing restricting delivery to victims in the target region. The macro injects architecture-aware shellcode into the host process through callback-based API abuse. 

The shellcode executes in chained XOR-encoded stages, each fetching and decoding the next from the same C2 domain under rotating file extensions (.ico, .mp3, .doc) to blend with normal traffic. The final stage drops a DLL implant that establishes scheduled-task persistence disguised as OneDrive telemetry, profiles the host, and beacons to a secondary C2 over HTTPS using AES-128-CBC. 

The C2 protocol runs a two-phase handshake: the implant registers with encrypted host data (CPU, OS version, hostname, installed software), and the server gates payload delivery based on that profile. By engaging the delivery endpoint directly, the team retrieved a live second-stage DoNot module (ejtest.dll) from active C2 infrastructure. This confirms that the C2 is serving real victims, not a dormant or test setup. The C2 is operational, and victims are currently receiving follow-on modules. 

The cryptographic and infrastructure overlap with prior DoNot operations indicates a sustained, ongoing threat to government and military organizations across South Asia. The Howler Cell Threat Research Team identified and analyzed this campaign against Bangladeshi military and defense targets, attributing it with high confidence to the DoNot group (also tracked as APT-C-35). This threat actor has been active since at least 2016, known for sustained cyber-espionage operations against government, military, and diplomatic targets across Pakistan, Bangladesh, Sri Lanka, and neighboring countries. 

The attribution is grounded in direct artifact overlap with previously documented DoNot operations. The strongest attribution evidence emerged from the second-stage module (ejtest.dll) retrieved directly from the active C2. Its hardcoded AES key and IV are byte-for-byte identical to those documented in an independent industry analysis of a DoNot sample, providing a definitive cryptographic linkage across campaigns. Additionally, the DLL agent's hardcoded C2 URI paths are identical to those observed in a separate DoNot sample documented by industry threat intelligence teams in late 2025. 

The use of the mopd= POST parameter for transmitting encrypted system reconnaissance and the beacon data structure collecting CPU model, OS version, hostname, and installed software is consistent across both samples, confirming a shared codebase.

🚀 [Read full article](https://www.cyderes.com/howler-cell/tracking-donot-apt-c-35-bangladesh-military-intrusion)