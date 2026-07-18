---
title: UAT-11795 Deploys Novel Starland RAT and Bespoke WLDR C2 Implant in Financially Motivated Campaign
date: 2026-07-16
categories: [CYBERSECURITY]
tags: [MALWARE,CYBERSECURITY,THREATS,STARLAND_RAT,WLDR_C2]
---

## Overview

Cisco Talos is disclosing **UAT-11795**, a sophisticated, Russian-speaking, financially motivated adversary that has been conducting a malicious campaign targeting users in the U.S. and Europe since at least June 2025. 🚨

Talos has discovered that the actor in this campaign delivers a Python-based remote access tool (RAT) that we track as **Starland RAT** and a command-and-control (C2) memory implant known as the **WLDR agent**. The WLDR agent is a sophisticated PowerShell-based C2 memory implant that features encrypted beaconing, task queuing, and a Runspace execution engine for executing additional payloads. UAT-11795 also has CastleStealer and Remcos RAT as alternative payload implants in their arsenal. The actor targets victims' credentials and cryptocurrency wallet assets, establishing a persistent connection to the victims' machines from the C2 server, with the potential to deliver and execute further payloads.

## Infection Observations

According to the telemetry data, the infection is predominantly observed in the United States. There are also fewer potential impacts observed in Germany, Romania, and Venezuela, based on the assessment of the passive DNS resolution data of the C2 domains associated with this campaign. 🌍

Talos has observed that the threat actor in this campaign has utilized trojanized installer lures from software categories including MobaXterm (SSH, remote desktop, and network administration terminal), Cisco WebEx and Zoom (enterprise video conferencing and collaboration platforms), DBeaver Community Edition (open-source database management and SQL client), and FACEIT (online gaming platform).

## Infrastructure Details

The threat actor in this campaign operates a distributed infrastructure across two functional categories, payload staging and persistent C2. The staging domains include **eorthopaedi[REACTED BY DNB EDITORS TO GET PAST GOOGLE FILTERS].com**, **web-dev[REACTED BY DNB EDITORS TO GET PAST GOOGLE FILTERS].com**, and **zynar[REACTED BY DNB EDITORS TO GET PAST GOOGLE FILTERS].io**. For instance, **eorthopaedi[REACTED BY DNB EDITORS TO GET PAST GOOGLE FILTERS].com** and **sast[REACTED BY DNB EDITORS TO GET PAST GOOGLE FILTERS].com** host the PowerShell stage chain under "/feed/" and "/alpha/" paths. **web-devto[REACTED BY DNB EDITORS TO GET PAST GOOGLE FILTERS].com** serves raw shellcode payloads under the paths ("/starlandfox", "/x32remka", "/dopfile") and a compressed archive. Furthermore, **zynar[REACTED BY DNB EDITORS TO GET PAST GOOGLE FILTERS].io** hosts the potential ClickFix-delivered HTML application (HTA) stager and trojanised installer lures.

## C2 Infrastructure

The C2 infrastructure for the Starland Python RAT includes the domains **windowscreenrepair[REACTED BY DNB EDITORS TO GET PAST GOOGLE FILTERS].com** (which is also likely to be a hijacked domain) and **aipythond[REACTED BY DNB EDITORS TO GET PAST GOOGLE FILTERS].com**. All C2 URLs incorporate a victim hardware identifier derived from the C: drive volume serial number of the victim machine as the final URL path component. The actor in this campaign has also implemented C2 infrastructure resilience by using a Polygon smart contract ("0x6ae382ed2154cc84c6672e4e908cd2c69c1b35ba"), which stores an XOR-encrypted fallback C2 domain that is retrievable via a public JSON-RPC call. Talos discovered that the actor controls two Telegram bots, **8384531459** ("skuefq_bot") and **7993597060** ("komandastuk_bot"), used for receiving the implant's execution notification beacons, including messages with victim's machine fingerprints and cryptocurrency wallet inventories.

For more details, check the full article here: [Read full article](https://blog.talosintelligence.com/uat-11795-deploys-novel-starland-rat-and-bespoke-wldr-c2-implant-in-financially-motivated-campaign).