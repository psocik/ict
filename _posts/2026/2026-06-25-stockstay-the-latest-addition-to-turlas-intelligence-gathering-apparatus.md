---
title: STOCKSTAY The Latest Addition to Turla's Intelligence Gathering Apparatus
date: 2026-06-25
categories: [CYBERSECURITY]
tags: [STOCKSTAY,TURLA,INTELLIGENCE,MALWARE,CYBERSECURITY]
---

## STOCKSTAY: The Latest Addition to Turla's Intelligence Gathering Apparatus 🚀

A significant proportion of STOCKSTAY operations observed by GTIG have been targeted at government or military organizations within Ukraine, consistent with Russian interests in relation to the ongoing conflict between the two countries. The threat actor has been observed utilizing in-country compromised infrastructure, including compromised government services, to deploy both STOCKSTAY and a range of supplementary payloads in support of these operations.

### Key Observations 🔍
- A smaller number of STOCKSTAY operations appear to have been targeted at European entities.
- STOCKSTAY was deployed following successful phishing attempts using malicious RDP configuration files.
- The RDP files were designed to create a connection from the victim's device to actor-controlled infrastructure, allowing the actor to deploy subsequent payloads.

### Technical Insights 💻
Through GTIG's visibility, we have identified that the threat actor uses STOCKSTAY at multiple distinct stages of their operations. Initially, STOCKSTAY is configured with hard-coded configuration passwords, which can be trivially extracted by analysts. Later, it incorporates environmental keying for its configuration, requiring the malware to be executed on a specific host, by a specific user, within a specific domain, or a predetermined combination of these attributes.

Additionally, overlaps with KAZUAR have been identified. In April 2025, GTIG observed STOCKSTAY being updated to implement a new string obfuscation mechanism based on an obscure pseudo-random number generation algorithm named "Squirrel3". In June 2025, GTIG noticed K1MORPHER code appearing in samples of KAZUAR.

As of late 2023, GTIG identified a similar separation of responsibilities within the STOCKSTAY ecosystem, with the same responsibilities being separated into distinct components. C2 communication is managed by the component tracked by GTIG as STOCKSTAY.STOCKBROKER, while task orchestration and execution are handled by STOCKSTAY.STOCKMARKET and STOCKSTAY.STOCKTRADER, respectively.

### Conclusion 📝
GTIG assesses with moderate confidence that STOCKSTAY and KAZUAR may be developed in part by a common developer or team, with active development occurring in tandem between the two malware ecosystems. We believe that STOCKSTAY is being developed in KAZUAR's image, with several design decisions likely stemming from the threat actor's wealth of experience in conducting operations using this long-standing toolkit.

[Read full article](https://cloud.google.com/blog/topics/threat-intelligence/stockstay-turla-intelligence-gathering/)