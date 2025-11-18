---
title: Dragon Breath Uses RONINGLOADER to Disable Security Tools and Deploy Gh0st RAT
date: 2025-11-17
categories: [RESEARCH]
tags: [DRAGON BREATH,RONINGLOADER,GH0ST RAT,CYBERSECURITY,APT-Q-27]
---

**Title**: Dragon Breath Uses RONINGLOADER to Disable Security Tools and Deploy Gh0st RAT  
**Source**: The Hacker News  
**Date Published**: November 17, 2025  

"Dragon Breath, a threat actor also known as APT-Q-27 and Golden Eye, is actively using a multi-stage loader dubbed RONINGLOADER to deliver a modified Gh0st RAT variant, primarily targeting Chinese-speaking users. Elastic Security Labs observed the campaign using trojanized NSIS installers disguised as legitimate applications like Google Chrome and Microsoft Teams. The group has been active since at least 2020 and is linked to the Miuuti Group, known for attacking online gaming and gambling sectors.  
...  
The infection chain employs a complex multi-stage delivery mechanism with numerous evasion techniques designed to neutralize endpoint security products prevalent in the Chinese market. According to researchers Jia Yu Chan and Salim Bitam, these techniques involve using a legitimately signed driver, deploying custom WDAC policies, and tampering with the Microsoft Defender binary via Protected Process Light (PPL) abuse. The initial malicious NSIS installers launch two further installers, one benign and the other, "Snieoatwtregoable.exe," triggering the attack chain by delivering a DLL and an encrypted file ("tp.png"). The DLL extracts shellcode from the PNG to launch another binary in memory.  
...  
RONINGLOADER attempts to remove userland hooks by loading a fresh "ntdll.dll" and elevate privileges via the "runas" command. It scans for antivirus solutions like Microsoft Defender, Kingsoft Internet Security, Tencent PC Manager, and Qihoo 360 Total Security, attempting to terminate those processes. For Qihoo 360, the malware blocks network communication by modifying firewall settings, injects shellcode into the Volume Shadow Copy (VSS) service process using PoolParty, and employs a signed driver ("ollama.sys") to terminate processes via a temporary service ("xererre1"). The loader also writes drivers to disk and creates temporary services to terminate other security processes.  
...  
After neutralizing security processes, RONINGLOADER runs batch scripts to bypass User Account Control (UAC) and create firewall rules blocking Qihoo 360 software. The malware also utilizes techniques exploiting PPL and Windows Error Reporting to disable Microsoft Defender Antivirus. Additionally, it targets Windows Defender Application Control (WDAC) by implementing a policy blocking Qihoo 360 and Huorong Security. The ultimate goal is to inject a malicious DLL into "regsvr32.exe" to conceal its activities and launch the Gh0st RAT payload into a high-privilege system process like "TrustedInstaller.exe."  
...  
The Gh0st RAT variant is designed to communicate with a remote server for instructions, enabling it to configure Windows Registry keys, clear event logs, download and execute files, alter clipboard data, run commands via "cmd.exe," inject shellcode into "svchost.exe," and execute payloads dropped to disk. It also includes a module for capturing keystrokes, clipboard contents, and foreground window titles. Unit 42 also identified two interconnected malware campaigns employing large-scale brand impersonation to distribute Gh0st RAT to Chinese-speaking users, highlighting the ongoing threat."  

To read the complete article see: [The Hacker News](https://thehackernews.com/2025/11/dragon-breath-uses-roningloader-to.html)  

There's still time to register for RISE-Malaysia next month: [RISE-Malaysia](https://www.team-cymru.com/events), and the one next February in San Francisco: [RISE-USA](https://go.team-cymru.com/rise-usa-2026)  
