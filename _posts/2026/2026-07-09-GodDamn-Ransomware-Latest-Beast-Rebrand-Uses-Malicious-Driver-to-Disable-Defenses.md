---
title: GodDamn Ransomware Latest Beast Rebrand Uses Malicious Driver to Disable Defenses
date: 2026-07-09
categories: [CYBERSECURITY]
tags: [RANSOMWARE,MALWARE,CYBERSECURITY,THREAT-HUNTING]
---

## GodDamn Ransomware: Latest Beast Rebrand Uses Malicious Driver to Disable Defenses

🚨 **Analysis of a recent GodDamn ransomware attack** indicates that this seemingly new ransomware is, in fact, the latest rebrand of the Beast ransomware, which itself was a rebrand of the Monster ransomware, first seen in 2022. The Symantec Threat Hunter Team tracks the developer behind these ransomware families as **Hyadina**. The GodDamn ransomware, which our analysts found has significant code overlap with Beast, was documented as being first seen on **May 21, 2026**, with the attack we investigated taking place around two weeks later, in early June.

During this attack, the threat actors leveraged **AnyDesk** for remote access, used a **NirSoft-based credential harvesting toolkit** comprising multiple different hacking tools and credential stealers, and employed a user-mode defense evasion tool disguised as a Symantec product along with the **PoisonX kernel driver** to disable endpoint defenses before deploying the ransomware.

### Key Findings
- The PoisonX kernel driver was first documented as being used to disable security software in early 2026.
- The driver is signed by Microsoft, making it appear legitimate to the system, allowing it to stop or disable security software at the kernel level.
- The earliest observed malicious activity occurred on **May 29, 2026**, when AnyDesk appeared on Computer 1 in a location inconsistent with a standard installation.

On **May 30, 2026**, the attackers deployed a defense evasion tool with the filename **symantec.exe**, staged in the user Music folder, designed to impersonate a Symantec product. This file dropped a signed kernel driver (PoisonX) into the system driver store, which can terminate security-product processes and remove user-mode API hooks, effectively disabling endpoint visibility on the host.

On **June 1, 2026**, lateral movement began across the enterprise network, with **PsExec** being used to push commands to remote targets. The attackers then launched the defense evasion tool and disabled **Windows Defender** real-time monitoring. By the end of **June 2**, this deployment sequence had been repeated across at least 10 hosts within the targeted organization. On **June 3, 2026**, the GodDamn ransomware, named **encrypter-windows-gui-x86.exe**, was first detected.

The four-day gap between the first observed pre-ransomware activity on **May 29** and the first ransomware detections on **June 3** is consistent with a dwell period during which the attackers may have staged payloads, exfiltrated data, or conducted additional reconnaissance before triggering the encryption phase.

For more details, check out the full article: [Read full article](https://symantec-enterprise-blogs.security.com/threat-intelligence/goddamn-ransomware-beast-rebrand)