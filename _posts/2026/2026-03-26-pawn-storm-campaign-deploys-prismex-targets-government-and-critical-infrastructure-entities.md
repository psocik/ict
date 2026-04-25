---
title: Pawn Storm Campaign Deploys PRISMEX, Targets Government and Critical Infrastructure Entities
date: 2026-03-26
categories: [CYBERSECURITY]
tags: [PAWN STORM,PRISMEX,CYBERSECURITY,MALWARE,APT]
---

## Overview

🚨 A prolific Russia-aligned Advanced Persistent Threat (APT) group known as Pawn Storm, also referred to as APT28, Fancy Bear, UAC-0001, and Forest Blizzard, has launched a new campaign deploying **PRISMEX**, a sophisticated collection of interconnected malware components. This operation primarily targets the defense supply chain of Ukraine and its allies, including the Czech Republic, Poland, Romania, Slovakia, Slovenia, and Turkey.

## Campaign Details

The campaigns have been active since at least **September 2025**, escalating significantly in **January 2026**. The focus is on Ukrainian defense and Western humanitarian and military aid infrastructure, which includes military allies, meteorological data providers, transport hubs, and international aid corridors.

### Technical Insights

PRISMEX utilizes advanced techniques such as:
- **Steganography**
- **Component Object Model (COM) hijacking**
- **Abuse of legitimate cloud services** for command and control.

TrendAI™ Research has identified PRISMEX as a collection of interconnected malware components, named for its steganographic characteristics. The components include:
- **PrismexDrop** (dropper)
- **PrismexLoader** (steganography loader)
- **PrismexStager** (Covenant Grunt implant)

These components are designed to evade modern Endpoint Detection and Response (EDR) systems through fileless execution and advanced steganography, with both espionage and potential sabotage functionalities observed, including wiper commands.

### Exploitation of Vulnerabilities

Pawn Storm has exploited multiple vulnerabilities, including a confirmed Windows zero-day (CVE-2026-21513). Their campaign in late January 2026 exploited the Microsoft Office vulnerability CVE-2026-21509, targeting government, military, and critical infrastructure entities across Central and Eastern Europe. The timeline indicates that the registration for CVE-2026-21509 began on **January 12, 2026**, two weeks prior to its public disclosure on **January 26, 2026**.

### Initial Access Vector

The PRISMEX campaign's initial access vector weaponizes CVE-2026-21509, a security feature bypass vulnerability in the Microsoft Office Object Linking and Embedding (OLE) mechanism. By embedding a specifically crafted OLE object within an RTF document, the attacker can force the host application to automatically initiate an outbound connection to retrieve and execute a remote .lnk (shortcut) file without requiring user interaction beyond opening the document.

### Conclusion

This sophisticated two-stage exploitation pattern suggests that Pawn Storm had access to vulnerability details ahead of public disclosure, indicating a high level of operational security and advanced planning.

To read the complete article see:
[Read full article](https://www.trendmicro.com/en_us/research/26/c/pawn-storm-targets-govt-infra.html)