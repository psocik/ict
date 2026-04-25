---
title: From open-source to open threat Tracking Chaos RAT’s evolution
date: 2025-06-04
categories: [MALWARE]
tags: [CHAOS RAT,MALWARE,CYBERSECURITY,THREAT ANALYSIS]
---

Acronis TRU identified new variants of Chaos RAT, a known malware family, in recent real-world Linux and Windows attacks.

Chaos RAT is an open-source remote administration tool (RAT) first seen in 2022. It evolved in 2024, and new samples have been discovered by TRU in 2025.

TRU researchers uncovered a critical vulnerability in Chaos RAT’s web panel that allows attackers to execute remote code on the server. This recent sample of Chaos RAT suggests that it lured victims to download a network troubleshooting utility for Linux environments.

Developed in Golang, Chaos RAT offers cross-platform compatibility with Windows and Linux systems — another clear example of how useful legitimate tools can contain vulnerabilities and be repurposed for cybercriminal activities.

While overall use remains limited, recent samples confirm Chaos RAT is still active. Its low detection profile creates opportunities for espionage, data exfiltration, and establishing footholds for ransomware and other post-compromise operations.

In this technical analysis, the Acronis TRU team focuses on a Linux variant and shares actionable detection strategies, including YARA rules, indicators of compromise, and threat-hunting tips with EDR for defenders.

To read the complete article see: [Full Article](https://www.acronis.com/en-us/cyber-protection-center/posts/from-open-source-to-open-threat-tracking-chaos-rats-evolution/) 