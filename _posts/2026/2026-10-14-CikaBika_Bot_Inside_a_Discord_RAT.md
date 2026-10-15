---
title: CikaBika Bot Inside a Discord RAT
date: 2026-10-14
categories: [CYBERSECURITY]
tags: [MALWARE,DISCORD,RAT,CIKABIKA,CYBERSECURITY]
---

## CikaBika Bot - Inside a Discord RAT 🚀

Darktrace malware researchers have discovered an ongoing malware campaign utilizing a document-themed lure that includes a malicious LNK file and a PDF with an embedded payload. The Nim-based loader deploys a Rust-based remote access trojan (RAT), employing a UAC bypass and DLL search-order hijacking technique targeting Microsoft Edge.

### Key Features of CikaBika Bot:
- **C2 Communication:** Utilizes Discord to create dedicated channels for managing infected devices and executing commands.
- **Functionality:** Supports system reconnaissance, remote command execution, screenshot capture, and file transfers.
- **Infection Chain:** Begins with a disk image and a malicious Windows shortcut. The malware is packaged within a disk image named `Proposition_Projet.img`, which contains a PDF titled `Presentation_Generale.pdf.pdf` and a Windows shortcut disguised as a Word document, `Proposition_Projet_Personnalisable.docx`.

### How It Works:
Opening the shortcut launches a hidden PowerShell process while displaying the PDF as a decoy. In the background, PowerShell reads the PDF as bytes and uses the value at offset 239 (0x20) as an XOR key to decode an embedded executable. The resulting payload is written to `%TEMP%\IfyuUapz.txt` and executed using `cmd /c`. This file is a Nim-based loader containing two Base64-encoded blobs: a Rust dynamic-link library (DLL) and a PowerShell deployment script.

The PowerShell component is responsible for moving the DLL to `C:\Program Files (x86)\Microsoft\Edge\Application\dbghelp.dll`. It first copies the DLL to `C:\Windows\Temp\dbghelp.tmp`, then modifies `HKCU\Software\Classes\ms-settings\shell\open\command` so that launching `computerdefaults.exe` can trigger a command to move the staged DLL into the protected Edge directory, attempting to bypass User Account Control (UAC).

### Exploitation:
The legitimate `msedge.exe` has a delay-loaded dependency on `dbghelp.dll`, and the malicious DLL exports a subset of the functions associated with Microsoft's debugging library. The attacker exploits this dependency through DLL search-order hijacking.

### RAT Functionality:
The malicious `dbghelp.dll` (IfyuUapz.txt) is a Rust-based RAT. Upon startup, the RAT registers the compromised device with Discord and begins collecting information about the host. Its reconnaissance routine gathers system details, runs `tasklist` to enumerate processes, executes `ipconfig` to obtain network configuration, and attempts to take a screenshot. The resulting artifacts include `tasklist_startup.txt`, `network_info.txt`, and `screenshot.png`.

The RAT uses Discord channels to send commands and report results, providing the attacker with an interactive command interface without the need for a dedicated C2 server. The command set includes:
- `!shell` for remote command execution
- `!sysinfo` and `!info` for host details
- `!isOn` for status checks
- `!tasklist` and `!ps` for process enumeration
- `!kill` for process termination
- File-transfer commands like `!upload` and `!download`
- Additional command handlers for screenshots (`!src`), camera access (`!camera`), streaming (`!stream`), and broadcasting (`!broadcast`).

During device registration, the malware retrieves the victim's public IP address using `ipify.com`. The registration message logs the device ID, hostname, registration time, private and public IP addresses, status, uptime, and the assigned Discord channel.

For more detailed information, you can read the complete article here: [Read full article](https://www.darktrace.com/blog/cikabika-bot-inside-a-discord-rat)\n