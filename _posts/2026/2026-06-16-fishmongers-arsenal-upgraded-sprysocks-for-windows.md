---
title: FishMonger's Arsenal Upgraded SprySOCKS for Windows
date: 2026-06-16
categories: [CYBERSECURITY]
tags: [MALWARE,CYBERSECURITY,FISHMONGER,SPRYSOCKS]
---

## FishMonger's Arsenal Upgraded: SprySOCKS for Windows 🚀

ESET researchers have discovered **SprySOCKS for Windows**, a backdoor weaponizing a kernel driver for advanced stealthiness. This malware is linked to **FishMonger**, a group believed to be operated by a Chinese contractor named **I-SOON**. While initially discovered on VirusTotal, ESET telemetry shows real activity between **2023 and 2024**, affecting several victims in **Honduras, Taiwan, Thailand, and Pakistan**, primarily targeting government organizations.

### Key Findings:
- The Windows variants are internally marked as **WIN_DRV** and **WIN_PLUS**.
- They come with a hardcoded C&C configuration and support communication over **TCP, UDP, and WebSocket protocols**.
- The core backdoor functionality includes support for over **30 C&C commands**, covering various functionalities such as:
  - System information collection
  - Process enumeration
  - Service management
  - File management functions (listing, creating, deleting, and transferring files)

### Advanced Stealth Techniques:
The **WIN_DRV** version utilizes kernel drivers to hide the malware's network connections, processes, files, and registry keys. It enables TCP traffic diversion, allowing operators to send commands through a random TCP port on the victim's device without exposing the backdoor's real listening port in the network traffic.

### Potential Threats:
Based on ESET telemetry, there are indications that some **SprySOCKS** attack scenarios may involve a **UEFI bootkit component**, possibly exploiting **CVE-2023-24932**.

**FishMonger** is categorized as a cyberespionage group under the **Winnti Group** umbrella, likely operating out of **Chengdu, China**. It is also known as **Earth Lusca, TAG-22, Aquatic Panda, or Red Dev 10**.

For more details, [Read full article](https://www.welivesecurity.com/en/eset-research/fishmongers-arsenal-upgraded-sprysocks-windows/)