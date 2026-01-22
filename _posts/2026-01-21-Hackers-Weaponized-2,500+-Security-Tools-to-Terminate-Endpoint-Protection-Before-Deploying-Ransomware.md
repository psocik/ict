---
title: Hackers Weaponized 2,500+ Security Tools to Terminate Endpoint Protection Before Deploying Ransomware
date: 2026-01-21
categories: [CYBER SECURITY]
tags: [RANSOMWARE,ENDPOINT PROTECTION,CYBER SECURITY,ADLICE SOFTWARE]
---

A large-scale campaign is turning a trusted Windows security driver into a weapon that shuts down protection tools before ransomware and remote access malware are dropped. The attacks abuse truesight.sys, a kernel driver from Adlice Software’s RogueKiller antivirus, and use more than 2,500 validly signed variants to quietly disable endpoint detection and response (EDR) and antivirus solutions across Windows systems.

The vulnerable TrueSight 2.0.2 driver exposes an IOCTL command that accepts attacker-controlled input and can forcibly kill chosen processes, including protected EDR agents and antivirus engines. Once the driver is loaded, the malware no longer has to fight user-mode tamper protections, because it operates directly in the Windows kernel with the same privileges as legitimate security software.

The impact is significant for defenders. With EDR agents shut down at the kernel level, telemetry stops, alerts never fire, and ransomware or remote access trojans can execute with almost no resistance. Victims often only notice the attack when files are already encrypted or data has been quietly exfiltrated. The scale of the driver variants and the high evasion rate against traditional antivirus make this technique especially dangerous for enterprises that rely on hash-based or signature-only defenses.

When ready, the module downloads the TrueSight driver if it is not already present, installs it as a Windows service (commonly named TCLService), and sends the crafted IOCTL request to terminate running security processes. With defenses gone, the final payload—often a HiddenGh0st remote access trojan or a ransomware family—runs with almost no visibility. From the initial phishing click to full system control, this sequence can complete in as little as 30 minutes, leaving a very small window for detection and response.

To read the complete article see: [Cyber Security News](https://cybersecuritynews.com/hackers-weaponized-2500-security-tools/) 

📅 RISE-USA: February 18-19, register at [Link](https://teamcymru.cventevents.com/riseusa) using the password "d7Jf#ga5Pr".

📅 RISE-IRELAND: April 14-15, register at [Link](https://teamcymru.cventevents.com/event/rise-ireland/) (no password).