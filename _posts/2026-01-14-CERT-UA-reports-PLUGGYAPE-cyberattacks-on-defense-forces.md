---
title: CERT-UA reports PLUGGYAPE cyberattacks on defense forces
date: 2026-01-14
categories: [APT]
tags: [CYBERSECURITY,PLUGGYAPE,MALWARE,UKRAINE,VOID BLIZZARD]
---

The Computer Emergency Response Team of Ukraine (CERT-UA) reported new cyberattacks against Ukraine’s defense forces using PLUGGYAPE malware.

Government experts attributed the attack with medium confidence to the Russian-linked group Void Blizzard (aka Laundry Bear, UAC-0190), active since 2024.

The attack chain starts with social engineering. Attackers contact targets through instant messaging apps and convince them to visit a fake website posing as a charitable foundation. The site encourages victims to download supposed “documents,” which are actually malicious executable files. These files often arrive inside password-protected archives or are sent directly via chat, using misleading extensions such as “.docx.pif” to appear harmless. When opened, the file runs a Python-based program packaged with PyInstaller. This program installs the PLUGGYAPE backdoor, giving attackers remote access to the infected system.

Later versions became more advanced. From December 2025, attackers deployed an obfuscated PLUGGYAPE.V2 variant using MQTT for communication and anti-analysis checks, hiding C2 server details on public sites in encoded form. In some cases, command-and-control server details are hidden and retrieved from public sites like Pastebin or rentry.co, often encoded to evade detection.

In May, the Netherlands General Intelligence and Security Service (AIVD) and the Netherlands Defence Intelligence and Security Service (MIVD) linked a previously undetected Russia-linked group, tracked as Laundry Bear (aka Void Blizzard), to a 2024 police breach. Threat actors broke into a police system and gained access to work-related contact details of multiple officers.