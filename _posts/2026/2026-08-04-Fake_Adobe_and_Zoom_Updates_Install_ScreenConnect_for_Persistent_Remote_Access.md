---
title: Fake Adobe and Zoom Updates Install ScreenConnect for Persistent Remote Access
date: 2026-08-04
categories: [CYBERSECURITY]
tags: [MALWARE,ADOBE,ZOOM,CYBERSECURITY,REMOTE_ACCESS]
---

## 🚨 Fake Adobe and Zoom Updates Alert!

Cybersecurity researchers have disclosed details of an active, multi-wave campaign that employs social engineering lures themed around Adobe and Zoom software updates, business document reviews, and system maintenance utilities to stealthily deploy Remote Monitoring and Management (RMM) programs like ConnectWise ScreenConnect. This campaign has been codenamed **SMOKE#SCREEN** by Securonix Threat Research.

### 🛡️ How It Works
The campaign relies on a toolkit of VBScript droppers, batch file loaders, compiled .NET executables, and an HTML phishing page, all ultimately pointing to a live WsgiDAV-based staging server. Successful attacks culminate with a ScreenConnect agent installed and beaconing to one of three attacker-controlled relay servers, providing the attackers with persistent remote access to compromised systems.

### 📧 Initial Access
The initial access vector is assessed to be spear-phishing, with the emails serving as a conduit for an obfuscated Visual Basic Script (VBScript) dropper that performs a series of environment and anti-analysis checks to ensure safe execution. If the checks pass, the script decrypts a PowerShell command that fetches a C# payload and executes it.

### 🔍 Delivery Strategy
The actor's delivery strategy has rotated across multiple trusted hosting services. An early phishing page delivers its payload via a Dropbox shared link, bypassing domain reputation filters since Dropbox is an allow-listed platform in most corporate environments. 

### ⚠️ Recommendations
To counter the threat, organizations are recommended to:
- Restrict execution of untrusted MSI files
- Monitor processes attempting to tamper with security products
- Audit legitimate use of RMM tools
- Check for suspicious PowerShell and "cmd.exe" processes
- Enforce strict UAC settings to prevent standard users from bypassing UAC prompts for administrative tasks

For more detailed information, you can read the complete article here: [Read full article](https://thehackernews.com/2026/08/fake-adobe-and-zoom-updates-install.html)