---
title: Hackers Can Inject Malicious Code into Antivirus Processes to Create a Backdoor
date: 2025-10-11
categories: [RESEARCH]
tags: [CYBER SECURITY,MALWARE,ANTIVIRUS]
---

A new technique enables attackers to exploit antivirus software by injecting harmful code directly into the antivirus processes. This approach makes it easier for them to evade detection and compromise the security that antivirus software is designed to provide.

This method, detailed by cybersecurity researcher Two Seven One Three on X (@TwoSevenOneT), involves cloning protected services and hijacking cryptographic providers to create a backdoor in the antivirus installation folder, bypassing standard defenses.

Injection occurs by hijacking the Windows Cryptography API, which antivirus processes use for encryption and signing. Modifying the registry key HKLM\SOFTWARE\Microsoft\Cryptography\Defaults\Provider to point to a malicious DLL triggers loading during service startup. To evade signature checks, the DLL is signed using cloned certificates from legitimate Windows programs, a method detailed in SpecterOps research.

This method’s implications are profound: malware could embed backdoors in antivirus environments, executing undetected. Prevention demands vigilant monitoring of module loads from anomalous paths, auditing trusted certificates in the registry, and enforcing PPL alongside behavioral analytics.

To read the complete article see: [Cyber Security News](https://cybersecuritynews.com/malicious-code-into-antivirus/) 

📅 Don't forget about our next conference in Kuala Lumpur on December 9th and 10th, 2025!