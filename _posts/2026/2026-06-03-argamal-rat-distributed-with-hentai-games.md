---
title: Argamal RAT Distributed with Hentai Games
date: 2026-06-03
categories: [MALWARE]
tags: [MALWARE,HENTAI,GAMING,SECURITY]
---

## Argamal RAT Distributed with Hentai Games 🚨

In April 2026, a new malware campaign targeting players of "hentai" games was discovered. Once launched, the infected games install a previously unknown malicious implant on the user's machine. After a few days, this implant downloads and executes a Trojan, leading to full system compromise and broad remote control capabilities for the attackers. This malware family has been dubbed **"Argamal"**.

The malware utilizes **COM hijacking** to persist on the victim's machine, replacing the InprocServer32 entry for the Windows Color System Calibration Loader DLL. This task is triggered upon user login, allowing the malware to run at startup.

### Distribution Methods 📦
In April, suspicious DLLs were found, with various versions existing since at least 2024. These DLLs were spawned by different hentai games (RenPy, RPG Maker MV). Distribution occurred via websites hosting download links redirecting to PixelDrain and through torrent trackers such as AniRena. Both methods delivered an archive containing the infected game, which included legitimate game files and a modified FFmpeg DLL (SHA1: 42add9475e67a1ccc6a6af94b5475d3defc01b85).

### Malware Functionality ⚙️
The natives2_blob.bin (SHA1: edce72f59e4c1d136cd1946af70d334c19df858d) executes a Base64-encoded PowerShell script, **Stage1**, when loaded. Stage1 performs basic checks for controlled environments (e.g., Sandboxie folder), establishing persistence if none are detected. It sets the MI_V environment variable to another Base64-encoded PowerShell script, **Stage2**, and modifies the InprocServer32 registry key to a random DLL filename. A scheduled task is created to execute Stage2 three days later.

Stage2 downloads an encrypted payload, **zaesdl.dat**, from GitHub using bitsadmin.exe. This payload is decrypted via AES-CBC, allowing the malware to run during every user session.

### Control and Communication 📡
The payload is a RAT with extensive functionality, checking for security solutions including Kaspersky, Avast, McAfee, BitDefender, and MalwareBytes. Default C2 servers are asper1[.]freeddns[.]org (earlier) or Winst0[.]kozow[.]com (latest), both pointing to 186[.]158.223.35. The C2 address can change; if the user's default locale is "zh-CN", the RAT sets its C2 to country1[.]ignorelist[.]com.

The payload sends UDP heartbeats to port 57441 of the C2, containing information like detected security solutions, system startup time, and machine IP. Based on C2 commands, the malware can execute commands, perform reboot/shutdown, control the cursor, take screenshots, compress files, and send files to specified servers, fully controlling the machine.

For more detailed information, you can read the full article here: [Read full article](https://securelist.com/argamal-rat-distributed-with-hentai-games/119999/)