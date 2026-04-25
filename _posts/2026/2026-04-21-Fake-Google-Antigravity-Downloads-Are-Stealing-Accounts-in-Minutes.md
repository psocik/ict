---
title: Fake Google Antigravity Downloads Are Stealing Accounts in Minutes
date: 2026-04-21
categories: [CYBERSECURITY]
tags: [MALWARE,GOOGLE,ANTIGRAVITY,CYBERSECURITY]
---

## 🚨 Fake Google Antigravity Downloads Alert!

Somebody went looking for Google's new Antigravity coding tool this week, clicked download, ran the installer, and got exactly what they thought they were getting. Antigravity installed cleanly. A shortcut appeared on the desktop. The application opened and worked. Nothing looked or felt wrong. But behind the scenes, that installer can give your accounts, your data, and even your machine to an attacker, without breaking anything the user can see.

Google Antigravity launched in November 2025 and has been one of the most searched-for developer tools on the web ever since; the real product lives at [antigravity.google](https://antigravity.google). Hardly anyone new to the product has the real URL memorized, so when a user reached a hyphenated lookalike (what researchers call a typosquat domain) at google-antigravity[.]com it was convincing enough at a glance.

The attacker didn't build a convincing fake; they took the genuine Antigravity installer, added one additional step to run their PowerShell script during setup, and repackaged the result. The malicious step is one extra line in the MSI's custom-action table, observed as a row named 'wefasgsdfg'. Antigravity installs properly, but the malicious part is happening quietly, in a folder they'll never open.

Somewhere in the middle of the install, the MSI runs a small helper script that drops two PowerShell files into the user's temporary folder: scr5020.ps1 and pss5032.ps1. The first file was added by the attacker, and it has one job: open an HTTPS connection to https://opus-dsn[.]com/login/, download whatever code the server sends back, and run it. Researchers call this pattern a downloader cradle, and its advantage to the attacker is flexibility.

The real payload lives on their server, not inside the installer out in the wild, so they can swap it out, change targeting, or turn the operation off without touching the file users are downloading. The cradle performs a DNS query for opus-dsn[.]com, a single TCP connection on port 443 to [REDACTED for DNB for Google filters] with a quiet HTTPS GET to /login/, and then the PowerShell process exited. The malware hadn't failed; it had introduced itself to the attacker's server and asked for code to run next--and whether the answer comes back is a decision the operator gets to make later, on their own time, one victim at a time.

When the server decides a target is worth attacking, the follow-on script first makes Defender look the other way. It calls Add-MpPreference to exclude %ProgramData%, %APPDATA%, and specific file types (.exe, .msi, .dll) and processes (PowerShell, msedge.exe, chrome.exe) from scanning. After collecting a profile of the machine and sending it to opus-dsn[.]com, the script also disables Windows' Antimalware Scan Interface by writing AmsiEnable=0 into HKLM\Software\Policies\Microsoft\Windows Script\Settings.

For persistence, it downloads 'secret.png' from https://captr.b-cdn[.]net/secret.png, saving it to C:\ProgramData\MicrosoftEdgeUpdate.png. This file, an AES-256-CBC ciphertext wrapping a .NET assembly, is loaded by a scheduled task, nearly indistinguishable from a real Microsoft Edge update task, registered to fire at every logon.

A second, non-persistent payload is also delivered. The decrypted assembly is a .NET stealer, scanning browsers, messaging apps, gaming platforms, FTP clients, and crypto wallets for Logins, Cookies, Autofills, and FtpConnections. Stolen session cookies enable attackers to bypass passwords and 2FA, leading to account takeover in minutes. The malware also includes capabilities for clipboard hijacking, keystroke logging, and 'hidden desktop' tradecraft.

For more details, check out the full article here: [Read full article](https://www.malwarebytes.com/blog/threat-intel/2026/04/fake-google-antigravity-downloads-are-stealing-accounts-in-minutes)