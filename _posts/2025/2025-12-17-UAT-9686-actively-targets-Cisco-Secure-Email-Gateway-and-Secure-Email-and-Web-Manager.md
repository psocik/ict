---
title: UAT-9686 actively targets Cisco Secure Email Gateway and Secure Email and Web Manager
date: 2025-12-17
categories: [APT]
tags: [CISCO,APT,UAT-9686,CYBERSECURITY]
---

Cisco Talos recently discovered a campaign targeting Cisco AsyncOS Software for Cisco Secure Email Gateway, formerly known as Cisco Email Security Appliance (ESA), and Cisco Secure Email and Web Manager, formerly known as Cisco Content Security Management Appliance (SMA). We assess with moderate confidence that the adversary, who we are tracking as UAT-9686, is a Chinese-nexus advanced persistent threat (APT) actor whose tool use and infrastructure are consistent with other Chinese threat groups. This active targeting enables attackers to execute system-level commands and deploy a persistent Python-based backdoor, AquaShell. Cisco became aware of this activity on December 10, which has been ongoing since at least late November 2025. Our analysis indicates that appliances with non-standard configurations, as described in Cisco's advisory, are what we have observed as being compromised by the attack. 

As part of this activity, UAT-9686 deploys a custom persistence mechanism we track as “AquaShell” accompanied by additional tooling meant for reverse tunneling and purging logs.

AquaShell is a lightweight Python backdoor that is embedded into an existing file within a Python-based web server. The backdoor is capable of receiving encoded commands and executing them in the system shell. It listens passively for unauthenticated HTTP POST requests containing specially crafted data. AquaShell is delivered as an encoded data blob that is decoded and ultimately placed in "/data/web/euq_webui/htdocs/index.py". Additionally, UAT-9686 utilizes AquaTunnel, a compiled GoLang ELF binary based on the open-source “ReverseSSH” backdoor. AquaTunnel creates a reverse SSH connection from the compromised system back to an attacker-controlled server, enabling unauthorized remote access. AquaPurge removes lines containing specific keywords from the log files specified. Chisel, another open-source tunneling tool, allows an attacker to proxy traffic through a compromised edge device, enabling them to easily pivot into the internal environment.

Talos assesses with moderate confidence that this activity is being conducted by a Chinese-nexus threat actor, which we track as UAT-9686. We have observed overlaps in tactics, techniques and procedures (TTPs), infrastructure, and victimology between UAT-9686 and other Chinese-nexus threat actors Talos tracks. Tooling used by UAT-9686, such as AquaTunnel (aka ReverseSSH), also aligns with previously disclosed Chinese-nexus APT groups such as APT41 and UNC5174. The tactic of using a custom-made web-based implant such as AquaShell is increasingly being adopted by highly sophisticated Chinese-nexus APTs. Customers are strongly advised to follow the guidance published in the security advisories. All IOCs, including IPs and file hashes associated with this campaign, have been blocked across the Cisco portfolio. Key indicators of compromise include: 2db8ad6e0f43e93cc557fbda0271a436f9f2a478b1607073d4ee3d20a87ae7ef (AquaTunnel), 145424de9f7d5dd73b599328ada03aa6d6cdcee8d5fe0f7cb832297183dbe4ca (AquaPurge), 172[.]233[.]67[.]176, and 38[.]54[.]56[.]95.

To read the complete article see: [Full Article](https://blog.talosintelligence.com/uat-9686/) 

🔗 **Conference Registration:** Apply for our first conference of next year in San Francisco on February 18th and 19th, 2026 at [Conference Link](https://teamcymru.cventevents.com/riseusa) using the password "d7Jf#ga5Pr", no quotes. 

📢 **Call for Papers:** If you have a case study or a workshop, our call for papers is open till the end of December: [Call for Papers Link](https://www.cvent.com/c/abstracts/c3f8ffd0-edef-43b4-9fa6-49be9e20e6c8) 

🛡️ **LEO Training Application:** To apply for the LEO training at this event: [LEO Training Application](https://cymru.wufoo.com/forms/riseusa-2026-leo-training-application/) (you MUST currently be a Law Enforcement Officer).