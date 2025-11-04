---
title: Hackers Deliver SSH-Tor Backdoor Via Weaponized Military Documents in ZIP Files
date: 2025-11-03
categories: [CYBER SECURITY]
tags: [CYBER ATTACK,SSH-TOR BACKDOOR,DEFENSE SECTOR,CYBERSECURITY]
---

In October 2025, threat researchers at Cyble Research and Intelligence Labs uncovered a sophisticated cyber attack leveraging weaponized military documents to distribute an advanced SSH-Tor backdoor targeting defense sector personnel.

Cyble analysts identified that the malware deploys OpenSSH for Windows alongside a customized Tor hidden service featuring obfs4 traffic obfuscation, granting threat actors anonymous access to SSH, RDP, SFTP, and SMB protocols on compromised systems.

The attack chain employs nested ZIP archives and LNK file disguises to bypass automated detection systems with remarkable sophistication.

Cyble analysts identified critical anti-analysis checks embedded within the second-stage PowerShell script. The malware validates that at least 10 recent LNK files exist on the system and confirms the process count exceeds 50—thresholds rarely met in sandbox environments.

To read the complete article see: [Cyber Security News](https://cybersecuritynews.com/hackers-deliver-ssh-tor-backdoor/) 👉.