---
title: Earth Sirrush A Russia-Aligned Intrusion Set With 4 Years of Evolving Espionage Tooling
date: 2026-10-08
categories: [CYBERSECURITY]
tags: [EARTH SIRRUSH,RUSSIA,ESPIONAGE,MALWARE,CYBERSECURITY]
---

## Earth Sirrush: A Russia-Aligned Intrusion Set With 4 Years of Evolving Espionage Tooling

**Source:** TrendAI Security  
**Date Published:** October 8, 2026  

Since at least 2022, the Russia-aligned intrusion set tracked by TrendAI™ Research as **Earth Sirrush** has conducted sustained spear-phishing campaigns against Ukrainian government agencies, defense organizations, border guard units, and logistics operators. This actor continually replaces its malware while retaining recognizable development, delivery, and infrastructure patterns.

### Evolution of Tools  
Earth Sirrush's early campaigns relied on PowerShell- and Go-based tools, including the **LONEPAGE**, **SEAGLOW**, and **OVERJAM** families. Between 2024 and 2025, the group shifted toward compiled C# malware, introducing **MATCHBOIL**, **MATCHWOK**, and **DRAGSTARE**, which are designed for loading payloads, executing encrypted tasking, stealing credentials, and performing system reconnaissance. The group's most notable development during this period was a previously undocumented .NET infostealer and remote access trojan (RAT) named **ASHVEIN**, which its developers referred to as "TelemetryBrowser." ASHVEIN targets Ukrainian government personnel and combines credential theft from Chrome and Firefox using DPAPI with GDI-based screenshot capture, file enumeration and retrieval, PowerShell remote shell execution, system fingerprinting through WMI queries, and encrypted C&C communications. ASHVEIN also includes detection of security analysis tools such as Wireshark, IDA, OllyDbg, Fiddler, and Process Monitor. Some ASHVEIN variants use a GitHub-based dead-drop resolver as a fallback mechanism, while delivery methods include DLL sideloading, VHD containers, and dedicated .NET droppers.

### Recent Developments  
In 2026, Earth Sirrush expanded its use of image-based steganography. The **CINDERBLOT** campaign, also known as **BadPaw**, used phishing lures impersonating the State Border Guard Service of Ukraine. The extracted payloads were hidden inside PNG images and deployed through scheduled tasks. In July 2026, CERT-UA documented a new delivery chain involving three tools: **LUNCHPOKE**, a malicious Notepad++ plugin; **BURNYBEAR**, a .NET loader; and **MATCHBOIL.V2**, an updated loader with stronger encryption and revised obfuscation. LUNCHPOKE uses DLL proxying to execute malicious code when the application starts. The campaign also abused renamed copies of schtasks.exe and created scheduled tasks that ran at short intervals. These techniques demonstrate a consistent operational goal: Hide malware inside familiar software, legitimate-looking documents, and ordinary Windows locations.

### Conclusion  
Although Earth Sirrush has repeatedly rebuilt its tooling, TrendAI™ Research identified several independent indicators connecting the campaigns. These include the reuse of the same PKCS #7 signature file as a social engineering prop, recurring developer account names and PDB path artifacts, and Russian-language indicators. Additionally, structurally identical XOR-based string encryption was observed across ASHVEIN, MATCHBOIL, and DRAGSTARE, alongside identical WMI fingerprinting queries across ASHVEIN.

[Read full article](https://www.trendaisecurity.com/en-us/resources-insights/trendai-security-blog/earth-sirrush-russia-aligned-intrusion-set-4-years-evolving-espionage-tooling)