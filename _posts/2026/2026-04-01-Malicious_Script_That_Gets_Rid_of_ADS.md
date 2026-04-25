---
title: Malicious Script That Gets Rid of ADS
date: 2026-04-01
categories: [CYBERSECURITY]
tags: [MALWARE,ADS,POWERSHELL,SECURITY]
---

## Malicious Script That Gets Rid of ADS 🚨

Today, most malware are referred to as **"fileless"** because they aim to minimize their footprint on the infected computer's filesystem. However, they still need to write something for persistence. The registry can serve as an alternative storage location. 

Some scripts continue to rely on files executed at boot time. For instance, a malicious script can add persistence using the following command:

```bash
reg add "HKCU\Software\Microsoft\Windows\CurrentVersion\Run" /v csgh4Pbzclmp /t REG_SZ /d "\"%APPDATA%\Microsoft\Windows\Templates\dwm.cmd\"" /f >nul 2>&1
```

The file located in `%APPDATA%` will be executed at boot time.

From the attacker's perspective, the original script copies itself with the command:

```bash
copy /Y "%~f0" "%APPDATA%\Microsoft\Windows\Templates\dwm.cmd" >nul 2>&1
```

Immediately after this copy operation, a PowerShell one-liner is executed:

```bash
powershell -w h -c "try{Remove-Item -Path '%APPDATA%\Microsoft\Windows\Templates\dwm.cmd:Zone.Identifier' -Force -ErrorAction SilentlyContinue}catch{}" >nul 2>&1
```

This PowerShell command attempts to remove the alternate-data-stream (ADS) `:Zone.Identifier` that Windows adds during file operations. 

The `:Zone.Identifier` indicates the source of the file (0 = My Computer, 1 = Local intranet, 2 = Trusted sites, 3 = Internet, 4 = Restricted sites). It remains unclear whether a "copy" will drop or conserve the ADS. Although the author could not find official Microsoft documentation, they noted that an LLM might incorrectly state that ADS are not preserved. In a Windows 10 lab, a downloaded copy of BinaryNinja had an ADS added to the file, and after copying it to "test.ext", the new file still retained the ADS!

By removing the ADS, the malicious script makes the file appear less suspicious during scans for "downloaded" files, a common operation in DFIR investigations. Ultimately, the script will invoke another PowerShell command that drops a DonutLoader on the victim's computer.

[Read full article](https://isc.sans.edu/forums/diary/Malicious%20Script%20That%20Gets%20Rid%20of%20ADS/32854/)