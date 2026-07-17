---
title: ThreatsDay Game Cheat Spyware, 24-Hour Ransomware, Chrome Sync Stalking + 12 More Stories
date: 2026-07-16
categories: [CYBERSECURITY]
tags: [MALWARE,RANSOMWARE,CYBERSECURITY,SPYWARE,THREATS]
---

## ThreatsDay: Game Cheat Spyware, 24-Hour Ransomware, Chrome Sync Stalking + 12 More Stories

🚨 **New Spirals ransomware** recently encrypted a victim network in South Asia within 24 hours of the initial breach. An IT services company was targeted by this previously undocumented ransomware family in June 2026. Broadcom's Symantec and Carbon Black Threat Hunter Team stated, "The Rust-based payload is either a new ransomware threat or one purpose-built for this attack." They added, "Less than 24 hours after the initial breach, the ransomware payload was being pushed to machines on the network."

The attacker gained initial access by compromising an internet-facing IIS web server and uploading an ASP.NET web shell. Over the next three hours, they established persistent access, conducted reconnaissance, uninstalled endpoint security software, dumped the Security Account Manager (SAM) hive, and set up covert remote access prior to deploying the payload across the network using PsExec.

Additionally, the U.S. Cybersecurity and Infrastructure Security Agency (CISA) has added CVE-2026-46817, an improper privilege management vulnerability in Oracle E-Business Suite, and CVE-2023-4346, an overly restrictive account lockout mechanism vulnerability in KNX Association KNX Protocol Connection Authorization Option 1, to its Known Exploited Vulnerabilities (KEV) catalog. Federal agencies are required to apply the fixes by July 18 and 29, 2026, respectively, for these actively exploited flaws.

In another campaign, **UAT-11795**, a sophisticated, Russian-speaking, financially motivated adversary, has been observed conducting malicious activity targeting users in the U.S. and Europe since at least June 2025. This activity delivers a Python-based remote access tool (RAT) dubbed **Starland RAT** and a command-and-control (C2) memory implant known as **WLDR agent**. These are delivered using trojanized installer lures for software like developer tooling, IT administration utilities, enterprise collaboration platforms, and consumer gaming applications (e.g., MobaXterm, WebEx, Zoom, DBeaver, and FaceIT).

Cisco Talos noted, "The WLDR agent is a sophisticated PowerShell-based C2 memory implant that features encrypted beaconing, task queuing, and a Runspace execution engine for executing additional payloads." UAT-11795 has also been linked to the deployment of **CastleStealer** and **Remcos RAT**. The malware is designed to target victims' credentials and cryptocurrency wallet assets, harvest Active Directory information, and establish a persistent connection to the victims' machines from the C2 server, likely with an aim to deliver and execute further payloads. The majority of the infections are in the U.S., with fewer potential impacts recorded in Germany, Romania, and Venezuela.

Separately, cybersecurity researchers identified **11 malicious NuGet packages** published as .NET command-line tools that present themselves as game utilities, bots, and "panels." Each of these acts as a first-stage downloader responsible for fetching and executing a second-stage Python payload named **"pepesoft.exe"** from GitHub Releases and Hugging Face paths under the username **"pepegit666,"** along with a dormant BitTorrent fallback mechanism built into it. Socket revealed that "The recovered payloads use downloader-supplied AWS-style key material to retrieve remote configuration, authenticate to Google Sheets, bind activations to hardware, and honor a remote HWID/UUID ban-list." In addition, "In the three direct-bytecode payloads, the larger game-automation application also exposes Telegram bot commands that can send screenshots back to the configured chat."

[Read full article](https://thehackernews.com/2026/07/threatsday-game-cheat-spyware-24-hour.html)