---
title: Before ToolShell Exploring Storm-2603’s Previous Ransomware Operations
date: 2025-07-31
categories: [APT]
tags: [RANSOMWARE,STORM-2603,CHECK POINT]
---

**Key Findings**  
Check Point Research (CPR) conducted a focused analysis of Storm-2603, a threat actor associated with recent ToolShell exploitations, together with other Chinese APT groups.  

Storm-2603 utilizes a custom malware Command and Control (C2) framework dubbed internally by the attacker as “ak47c2”. This framework includes at least two different types of clients: HTTP-based (dubbed by us “ak47http”) and DNS-based (dubbed by us “ak47dns”).  

Based on VirusTotal data, Storm-2603 likely targeted some organizations in Latin America throughout the first half of 2025, in parallel to attacking organizations in APAC.  

Some of the actor’s TTPs align with many other ransomware groups, and involve open-source tools such as PsExec and masscan. In addition, the threat actors use a custom tool that leverages the BYOVD (Bring Your Own Vulnerable Driver) technique to tamper with endpoint protections.  

Storm-2603 attacks involved multiple ransomware families, sometimes bundled together. Those are commonly deployed by abusing DLL hijacking.  

To read the complete article see:  
[Before ToolShell: Exploring Storm-2603’s Previous Ransomware Operations](https://research.checkpoint.com/2025/before-toolshell-exploring-storm-2603s-previous-ransomware-operations/) 