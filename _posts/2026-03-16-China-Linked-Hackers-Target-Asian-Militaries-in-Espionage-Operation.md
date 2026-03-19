---
title: China-Linked Hackers Target Asian Militaries in Espionage Operation
date: 2026-03-16
categories: [CYBERSECURITY]
tags: [CHINA,HACKERS,ESPIONAGE,MILITARY,CYBERSECURITY]
---

## China-Linked Hackers Target Asian Militaries in Espionage Operation 🚀

Southeast Asian military organizations have been targeted in a China-linked cyberespionage campaign running for years, as reported by Palo Alto Networks. This campaign, likely ongoing since at least 2020 and attributed to a state-sponsored threat actor tracked as CL-STA-1087, demonstrates a high degree of patience, with attackers remaining dormant in compromised environments for months.

The attackers actively searched for and collected highly specific files concerning military capabilities, organizational structures, and collaborative efforts with Western armed forces. 

### Intrusion Techniques 🔍

As part of the observed intrusions, the hackers deployed custom tools, such as the **AppleChris** and **MemFun** backdoors, along with the **Getpass** credential stealer. They executed malicious PowerShell scripts remotely on multiple infected systems, creating reverse shells to a command-and-control (C&C) server and dropping the AppleChris backdoor. The attackers also relied on WMI and native Windows .NET commands to infect domain controllers, web servers, IT workstations, and executive-level systems.

### Variants of Malware 🦠

The threat actor deployed multiple variants of the AppleChris backdoor, including an earlier development iteration that used a Dropbox account and a Pastebin as the dead drop resolvers. Another variant, known as Tunneler, relied solely on Pastebin but added advanced network proxy capabilities. Additionally, they deployed MemFun, a multi-stage malware family that uses reflective DLL loading for executing the main backdoor. Furthermore, they were seen deploying Getpass, a custom version of Mimikatz targeting 10 specific Windows authentication packages for credential harvesting.

### Operational Schedule ⏰

Palo Alto Networks’ investigation revealed that the attackers’ operational schedule aligns with a UTC+8 time zone, which represents typical office hours across China and other Asian regions. The targeting of military organizations in Southeast Asia, the use of China-based cloud network infrastructure, and the use of Simplified Chinese on a login page for a C&C server suggest that the state-sponsored group behind this campaign is likely operating out of China.

To read the complete article see: [Read full article](https://www.securityweek.com/china-linked-hackers-hit-asian-militaries-in-patient-espionage-operation/)