---
title: New Lindnor Backdoor and Glut of Security Killers Used in Ransomware Attack on U.S. Org
date: 2026-11-05
categories: [CYBERSECURITY]
tags: [RANSOMWARE,MALWARE,SECURITY,ANUBIS,BACKDOOR]
---

## New Lindnor Backdoor and Glut of Security Killers Used in Ransomware Attack on U.S. Org 🚨

Attackers using the **Anubis ransomware** targeted a U.S. organization in **October 2026** with a new custom backdoor known as **Backdoor.Lindnor**. Fortunately, the attack was thwarted before the encryption phase could begin. The backdoor cleverly masqueraded as a Chrome component and a VMware file, and was detected on two Microsoft SQL Server machines.

### Attack Details 🔍
Within roughly an hour, the attackers deployed at least **13 executables** aimed at terminating security services, alongside five publicly known vulnerable drivers. They also installed the legitimate remote access tool **AnyDesk** and a separate tool to run it in **Safe Mode**, likely to maintain access when security software was not fully operational. Thankfully, the file encryption payload was blocked from execution, and there is no evidence that any files were encrypted.

### Background on Anubis Ransomware 🦠
Anubis has claimed approximately **96 victims** in the past 12 months, with **52%** of those victims located in the U.S. This ransomware is developed by a group tracked by Symantec as **Hawkmoth**, which operates a ransomware-as-a-service (RaaS) model that rebranded from the **Sphinx ransomware** in December 2024.

### Notable Aspects of the Attack ⚠️
The presence of this backdoor is significant, as custom backdoors are relatively uncommon in ransomware attacks. The backdoor was installed under the filename **healthcontroller64.exe** in a folder designed to resemble a Chrome component unpacker directory, and as **svchelper.exe** in a VMware folder on another machine. In both instances, the backdoor appeared to run as a service.

A striking feature of this attack was the rapid deployment of at least **13 executables** to disable security products. The attackers favored the **Bring Your Own Vulnerable Driver (BYOVD)** approach, dropping five signed but vulnerable drivers to gain kernel-level access. Two of these executables, **gbbsym.exe** and **symgooq.exe**, disguised themselves as Symantec software. Eleven of the 13 executables were previously unpublished, indicating a methodical approach to finding effective tools.

### Conclusion 🛡️
The attackers also configured AnyDesk to operate in **Safe Mode**, allowing them to bypass security measures. This incident highlights the evolving tactics of ransomware groups and the need for robust security measures to counteract such sophisticated attacks.

For more detailed information, you can read the full article here: [Read full article](https://www.security.com/threat-intelligence/lindnor-new-backdoor-anubis-ransomware)