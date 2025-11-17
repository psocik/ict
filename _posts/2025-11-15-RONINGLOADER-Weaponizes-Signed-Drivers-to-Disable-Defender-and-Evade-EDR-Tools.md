---
title: RONINGLOADER Weaponizes Signed Drivers to Disable Defender and Evade EDR Tools
date: 2025-11-15
categories: [CYBER SECURITY]
tags: [RONINGLOADER,SIGNED DRIVERS,CYBER SECURITY,MALWARE,EDR]
---

**Source:** Cyber Security News  

RONINGLOADER, a multi-stage loader spreading a modified version of the gh0st RAT, uses clever tricks to bypass antivirus protection. This campaign shows how attackers are getting better at breaking through security defenses. The malware brings its own signed driver that looks legitimate to Windows but actually helps it kill security processes.

To kill these processes, RONINGLOADER uses a signed driver called **ollama.sys** that was digitally signed by **Kunming Wuqi E-commerce Co., Ltd.** The driver registers a single function that accepts a process ID and terminates it using kernel-level APIs that normal security tools cannot block. The malware writes this driver to disk, creates a temporary service to load it, sends the termination command, and immediately deletes the service.

For **Qihoo 360**, the malware takes extra steps by blocking all network connections through firewall rules before injecting code into the Volume Shadow Copy service process. This injection uses Windows thread pools with file write triggers, a technique that helps it avoid detection.

To read the complete article see: [RONINGLOADER Weaponizes Signed Drivers](https://cybersecuritynews.com/roningloader-weaponized-weaponizes-signed-drivers/) 🎉