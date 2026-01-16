---
title: Gootloader now uses 1,000-part ZIP archives for stealthy delivery
date: 2026-01-15
categories: [MALWARE]
tags: [GOOTLOADER,MALWARE,CYBERSECURITY]
---

The Gootloader malware, typically used for initial access, is now using a malformed ZIP archive designed to evade detection by concatenating up to 1,000 archives. In doing so, the malware, which is an archived JScript file, causes many tools to crash when trying to analyze it. According to researchers, the malicious file is successfully unpacked using the default utility in Windows, but tools relying on 7-Zip and WinRAR fail.

To achieve this, the threat actor behind the malware concatenates between 500 and 1,000 ZIP archives and also uses other tricks to make parsing from analysis tools more difficult. The Gootloader malware loader has been active since 2020 and is used by various cybercriminal operations, including ransomware deployments.

After a seven-month break, the operation returned last November, as reported by security researchers at Huntress Labs and the DFIR Report. To further strengthen the anti-analysis of this stage, Gootloader operators have implemented more extensive obfuscation mechanisms, according to Expel researchers.

Once executed on the host, the malware’s JScript activates via Windows Script Host (WScript) from a temporary directory and establishes persistence by adding shortcut (.LNK) files to the Startup folder that point to a second JScript file. The researchers recommend that defenders change the default application for opening JScript files to Notepad instead of Windows Script Host, to prevent their execution. To reduce the attack surface, Expel advises blocking wscript.exe and cscript.exe from executing downloaded content if JScript files are not needed.

*To read the complete article see:* [Gootloader now uses 1,000-part ZIP archives for stealthy delivery](https://www.bleepingcomputer.com/news/security/gootloader-now-uses-1-000-part-zip-archives-for-stealthy-delivery/).