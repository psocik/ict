---
title: CL-STA-1062 Targets Southeast Asian Governments and Critical Infrastructure
date: 2026-06-26
categories: [CYBERSECURITY]
tags: [SOUTHEAST ASIA,CYBERSECURITY,MALWARE,CRITICAL INFRASTRUCTURE]
---

## Overview of CL-STA-1062

Throughout 2025, we observed a cluster of activity targeting government entities and critical infrastructure in Southeast Asia. Specifically, the activity targeted state-owned enterprises in the energy and government sectors. The Chinese-speaking attackers behind this cluster, which we track as CL-STA-1062, have been active since at least March 2022. We assess with high confidence that this is the same cluster, known as UAT-7237, that was reported for its campaigns against web hosting infrastructure in Taiwan in mid-2025. 

## Attack Techniques

From a technical standpoint, the attackers behind CL-STA-1062 rely on a hybrid toolkit. While they frequently use common open-source tools such as **SoftEther VPN**, **Mimikatz**, and **VNT**, they have recently introduced **TinyRCT**, a bespoke, previously undocumented backdoor. 

Our investigation into CL-STA-1062 activity highlights a broader long-term strategy in the Asia-Pacific region. In September 2025, we discovered that the attackers had compromised a Southeast Asian government entity by deploying web shells and exfiltrating database information. 

## Intrusion Details

During this intrusion, the attackers were also able to conduct network reconnaissance on a separate government entity in the same country. Between October and December 2025, we observed the likely compromise of at least ten different organizations in Southeast Asia. Since mid-2025, the threat actor behind CL-STA-1062 focused on critical infrastructure, indicating a sustained regional focus. 

## Tools and Malware

The intrusions we observed typically begin with the attackers exploiting web applications to deploy ASPX web shells. From this foothold, the activity includes open-source tools and custom malware. The attackers frequently use tunneling tools for command and control (C2) and data exfiltration. They deployed a variety of these tools, including **SoftEther VPN**, **VNT**, **yuze**, and **Mimikatz**. 

To escalate privileges, the attackers deployed known open-source tools, such as **JuicyPotato**. For data staging and exfiltration, they frequently compressed findings into password-protected RAR archives. 

## TinyRCT Backdoor

TinyRCT is a lightweight, C#-based remote access Trojan (RAT) targeting Windows. It operates as a backdoor, enabling attackers to execute arbitrary system commands, exfiltrate files, capture screenshots, and remotely manage the infected host. Upon execution, the malware performs an environment validation to explicitly verify that it was executed from `%LOCALAPPDATA%`. 

If the malware was executed from any other location, such as a sandbox environment or a malware analyst's desktop, the binary terminates immediately. After successful registration, TinyRCT establishes a persistent communication channel with the C2 server. The malware uses standard HTTP for network traffic but encrypts all exchanged data using AES-128 encryption in CBC mode. 

The backdoor executes a concise set of commands, including shell execution, file listing, file exfiltration, screen capture, and a self-destruct mechanism.

For more detailed information, you can read the full article [here](https://unit42.paloaltonetworks.com/cl-sta-1062-tinyrct-backdoor/).