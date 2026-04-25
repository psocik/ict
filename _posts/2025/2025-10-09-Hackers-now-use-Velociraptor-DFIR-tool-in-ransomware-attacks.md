---
title: Hackers now use Velociraptor DFIR tool in ransomware attacks
date: 2025-10-09
categories: [SECURITY]
tags: [RANSOMWARE,DFIR,VELOCIRAPTOR,LOCKBIT,BABUK]
---

Threat actors have started to use the Velociraptor digital forensics and incident response (DFIR) tool in attacks that deploy LockBit and Babuk ransomware.

In the first stage of the attack, the threat actor created local admin accounts that were synced to Entra ID and used them to access the VMware vSphere console, giving them persistent control over the virtual machines (VMs). After gaining initial access, the actors installed an outdated version of Velociraptor (version 0.73.4.0) that was exposed to a privilege escalation vulnerability (CVE-2025-6264) that could lead to arbitrary command execution and endpoint takeover.

The researchers noted that Velociraptor helped the attackers maintain persistence, launching it multiple times, even after the host was isolated. Attackers disabled Defender real-time protection by modifying Active Directory GPOs and turned off behavior and file/program activity monitoring. Endpoint detection and response (EDR) solutions identified the ransomware deployed on Windows target systems as LockBit, but the extension for the encrypted files was ".xlockxlock," seen in Warlock ransomware attacks. On VMware ESXi systems, the researchers found a Linux binary that was detected as Babuk ransomware.

Before encrypting the data, the attacker used another PowerShell script to exfiltrate files for double-extortion purposes. The script uses ‘Start-Sleep’ to insert delays between uploading actions to evade sandbox and analysis environments.

To read the complete article see: [here](https://www.bleepingcomputer.com/news/security/hackers-now-use-velociraptor-dfir-tool-in-ransomware-attacks/) 😱.