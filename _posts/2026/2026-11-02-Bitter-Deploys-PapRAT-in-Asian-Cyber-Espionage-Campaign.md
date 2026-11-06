---
title: Bitter Deploys PapRAT in Asian Cyber-Espionage Campaign
date: 2026-11-02
categories: [CYBERSECURITY]
tags: [CYBER-ESPIONAGE,MALWARE,PAPRAT,BITTER,FORTIGUARD]
---

## Bitter Deploys PapRAT in Asian Cyber-Espionage Campaign

A suspected South Asian cyber-espionage group has been observed pairing native Windows tools with a custom remote access trojan (RAT) dubbed **PapRAT** to maintain access to targeted organizations. Cara Lin of Fortinet's FortiGuard Labs detailed the campaign in research published on **November 2, 2026**, attributing it with high confidence to **Bitter**, also tracked as **TA397**, based on lure filenames, command-and-control (C2) patterns, file metadata, and malware analysis. FortiGuard Labs tracked the campaign over several months and described the targets as South Asian organizations, though its telemetry maps also show activity in Southeast Asia and South Korea. Lure files referred to a bilateral meeting request, an ambassador's letter about the 11th Belt and Road Summit, and a 2026 gala dinner invitation.

The campaign utilized three infection chains. The first chain took a living-off-the-land approach: a malicious Windows shortcut (LNK) file abused the built-in **ftp.exe** utility to run scripts and create scheduled tasks. Those tasks used **curl** to fetch fresh commands from attacker servers, and the chain deployed no traditional malware executable. FortiGuard Labs said operators could change their instructions on the server without pushing a new binary. "When an intrusion leverages trusted system processes, signature-based controls simply have nothing to alert on," said Shane Barney, CISO at Keeper Security. He argued for least-privilege access, tighter limits on native scripting engines, and the removal of standing administrative rights.

The other two chains delivered PapRAT through Windows Installer (MSI) packages, one hidden with a decoy spreadsheet in a virtual hard disk (VHDX) image and the other fetched via an internet shortcut in a RAR archive. The C++ build of PapRAT posed as a Microsoft component, beaconed over plaintext HTTP, and supported eight commands, including remote shell access, file transfers, and screenshots. A Rust variant obtained more recently switched to HTTPS and added three more, for PowerShell execution, pausing, and exiting. In the third chain, PapRAT downloaded **WmRAT**, a C++ RAT previously documented by other researchers, which FortiGuard Labs cited as a further indicator linking the campaign to Bitter. Jason Soroko, senior fellow at certificate lifecycle management firm Sectigo, said the Windows-tools route meant "a search for PapRAT alone could miss part of the campaign." He warned that deleting the first implant found might not remove the attacker.

FortiGuard's recommendations included handling unexpected LNK files, internet shortcuts, disk images, and MSI installers with care. In the first chain, though, FortiGuard found no PapRAT at all, only a shortcut file, Windows tools, scripts, and scheduled tasks.

[Read full article](https://www.infosecurity-magazine.com/news/paprat-bitter-cyberespionage/) 
