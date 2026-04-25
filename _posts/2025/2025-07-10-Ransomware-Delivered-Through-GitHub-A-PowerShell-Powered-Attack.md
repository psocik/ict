---
title: Ransomware Delivered Through GitHub A PowerShell-Powered Attack
date: 2025-07-10
categories: [SECURITY]
tags: [RANSOMWARE,GITHUB,POWERSHELL]
---

## Overview

Recently, the SonicWall Capture Labs threat research team identified a PowerShell-based ransomware variant that is abusing GitHub for its distribution. The malware authors are misusing raw.githubusercontent.com, a GitHub domain used to host raw content of unprocessed file versions. Additionally, the supporting executables (such as decryptor.exe) required for further functionality are also hosted on the GitHub repository of the malware authors.

The initial infection vector for the ransomware is an archive file containing the malicious LNK file. It is highly likely that this file reached the victim's machine via an email attachment. These LNK files are primarily Windows shortcut files that provide access to software located in other directories without directly launching the executable itself.

Here, the `Project_Workshop_7th_Minutes.txt.lnk` file points to `powershell.exe` and is embedded with predefined malicious parameters set by the attacker. Although the icon looks like a Notepad file, we can see it’s trying to execute PowerShell.

To read the complete article see: [Ransomware Delivered Through GitHub: A PowerShell-Powered Attack](https://www.sonicwall.com/blog/ransomware-delivered-through-github-a-powershell-powered-attack) 