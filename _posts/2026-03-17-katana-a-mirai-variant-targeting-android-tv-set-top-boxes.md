---
title: Katana A Mirai Variant Targeting Android TV Set-Top Boxes
date: 2026-03-17
categories: [CYBERSECURITY]
tags: [MALWARE,ANDROID,BOTNET,CYBERSECURITY]
---

## Katana: A Mirai Variant Targeting Android TV Set-Top Boxes

🚨 **Content Warning:** This report quotes malware artifacts verbatim, including domain names, C2 strings, and build paths chosen by the threat actors. Some contain crude or offensive language. These are reproduced exactly as found in samples to enable accurate detection and attribution.

This report documents the **Katana botnet**, a Mirai variant targeting Android TV set-top boxes through ADB exploitation. The devices it infects are low-cost, often unbranded boxes running the Android Open Source Project (AOSP) without Google Play Protect or official Google certification, not Google-branded Android TV products.

Katana is part of a growing wave of botnets exploiting the same attack surface: residential proxy services that expose internal networks, enabling mass ADB exploitation of Android TV devices. What sets Katana apart from the dozens of Mirai forks circulating on these devices is its technical complexity: it packages a DDoS bot with an on-device compiled kernel rootkit inside an Android APK, giving it persistence and stealth unusual for this class of malware. The bot self-identifies as **MIRAI** via its Busybox probe strings (`/bin/busybox MIRAI`).

Nokia Deepfield Emergency Response Team (ERT) observations indicate at least **30,000 active bots** based on network observations (lower-end estimate). The botnet is actively operational as of March 2026, with observed attack volumes reaching **150 Gbps**. Katana has no code or infrastructure overlap with Kimwolf, but the two families compete for the same pool of vulnerable devices, and Katana's aggressive bot killer and ADB port remapping reflect an ongoing turf war: multiple botnet operators are now fighting each other for control of the same pool of devices.

Katana employs aggressive environment control, where a locker process binds to ADB port **5555** and kills any new process not present at boot, blocking rival bots and forensic tools. The bot disables **100+ system utilities** via bind-mount blocking and remaps the ADB port, locking out both competitors and device owners. No scanner, no credential table; external ADB exploitation scripts handle propagation entirely, making this a pure DDoS payload.

Katana features rootkit compilation on-device; the APK ships **5 architecture-specific bot binaries** plus TinyCC and rootkit source code, compiling a kernel module (`wlan_helper.ko`) on each target device. The module hooks **5 syscalls** to hide the bot from process listings, prevent file deletion, and block signal delivery. Mirai derivatives almost never ship kernel modules; this is a notable escalation.

The C2 infrastructure utilizes encrypted C2 with runtime domain rotation. Three domains are encrypted via a custom **5-step cipher**; a fourth (`iloveyourweewee[.]bz`) is delivered at runtime. All resolve, at the time of writing, to bulletproof hosting at Omegatech (Seychelles). The C2 can push new domains without redeploying binaries.

Researchers retrieved the APK from the primary staging server `87.121.84[.]74:13121` in March 2026 and identified a secondary staging server at `45.153.34[.]187` (pfcloud.io) on **2026-03-16**. ThreatFox independently tags the C2 domains and IP addresses as "Mirai alias Katana" (first seen **2025-11-07** for the `satyr[.]wtf` scanner domain, **2026-02-22** for the current C2 infrastructure).

Katana uses **11 DDoS attack methods**, including protocol-specific floods targeting FiveM game servers (CitizenFX API), SSH services (PuTTY banner spoofing), MySQL authentication, SMTP relay, IRC, FTP, LDAP, TeamSpeak 3, and Valve Source Engine. The botnet also exhibits indicators of **AI-assisted development**. A **3-day self-destruct mechanism** removes all persistence if the C2 is unreachable, cleaning up SysVinit scripts, cron jobs, and bot binaries.

For more details, check out the full report: [Read full article](https://github.com/deepfield/public-research/blob/main/katana/report.md)