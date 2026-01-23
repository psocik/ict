---
title: Osiris - New Ransomware, Experienced Attackers?
date: 2026-01-22
categories: [SECURITY]
tags: [RANSOMWARE,CYBERSECURITY,THREAT INTELLIGENCE]
---

A new ransomware family called Osiris was used in an attack targeting a major food service franchisee operator in Southeast Asia in November 2025. Investigation by the Symantec and Carbon Black Threat Hunter Team found that this threat is unique and appears to be a completely new ransomware family. Nothing is known yet about who developed Osiris and if it is run as a ransomware-as-a-service (RaaS), but there are some indications that the attackers who used it were previously associated with Inc ransomware.

A wide range of living off the land and dual-use tools were used in this attack, including a malicious Poortry driver, which was likely part of a bring-your-own-vulnerable-driver (BYOVD) attack to disable security software. The attackers exfiltrated data to Wasabi buckets, and the use of a version of Mimikatz previously associated with Inc ransomware indicates potential links between this attack and those involving Inc.

Osiris has multiple typical ransomware functions and can stop services, specify which folders and extensions to encrypt, terminate processes, and drop a ransom note. It utilizes a hybrid encryption scheme: ECC + AES-128-CTR, appending the .Osiris extension to affected files. The first suspicious activity on the target’s network occurred days before deployment when Rclone was used for data exfiltration.

The attackers used other dual-use tools like Netscan, Netexec, and MeshAgent, deploying a modified version of the Rustdesk tool. They also used a malicious driver called Poortry, which has been linked to other attacks in the past. The use of Wasabi cloud service for exfiltration and tools previously used by Inc ransomware points to a sophisticated and experienced group behind this attack.

To read the complete article see: [Symantec](https://symantec-enterprise-blogs.security.com/threat-intelligence/new-ransomware-osiris).