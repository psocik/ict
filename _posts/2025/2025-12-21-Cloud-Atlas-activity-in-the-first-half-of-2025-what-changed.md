---
title: Cloud Atlas activity in the first half of 2025 what changed
date: 2025-12-21
categories: [MALWARE]
tags: [CLOUD ATLAS,PHISHING,KASPERSKY,MALICIOUS CODE]
---

Known since 2014, the Cloud Atlas group targets countries in Eastern Europe and Central Asia. Infections occur via phishing emails containing a malicious document that exploits an old vulnerability in the Microsoft Office Equation Editor process (CVE-2018-0802) to download and execute malicious code. In this report, we describe the infection chain and tools that the group used in the first half of 2025, with particular focus on previously undescribed implants.

The starting point is typically a phishing email with a malicious DOC(X) attachment. When the document is opened, a malicious template is downloaded from a remote server. The document has the form of an RTF file containing an exploit for the formula editor, which downloads and executes an HTML Application (HTA) file. In the given example, the malicious RTF file containing the exploit was downloaded from the URL hxxps://securemodem[.]com?tzak.html_anacid. The malicious HTA file extracts and creates several VBS files on disk that are parts of the VBShower backdoor. VBShower then downloads and installs other backdoors: PowerShower, VBCloud, and CloudAtlas. This infection chain largely follows the one previously seen in Cloud Atlas’ 2024 attacks.

Compared to the previous version, the VBShower::Backdoor runs additional downloaded VB scripts in the current context, regardless of the size. The VBShower::Payload (1) script collects information about running processes, including their creation time, caption, and command line. VBShower::Payload (2) is used to install the VBCloud implant. It downloads a ZIP archive and unpacks it into the %Public% directory. Then, it creates a scheduler task named “MicrosoftEdgeUpdateTask” to run the command: wscript.exe %Public%\Libraries\MicrosoftEdgeUpdate.vbs. The file MicrosoftEdgeUpdate.vbs is a launcher for VBCloud, which reads the encrypted body of the backdoor from upgrade.mds, decrypts it, and executes it. Almost the same script installs the CloudAtlas backdoor to "%LOCALAPPDATA%". In this case, a.xml, d.xml, and e.xml are the executable file and libraries of VLC Media Player. The c.xml file is a malicious library used in a DLL hijacking attack, where VLC acts as a loader, and the b.xml file is an encrypted body of the CloudAtlas backdoor.

Additionally, VBShower::Payload (3) creates a scheduler task to execute "%LOCALAPPDATA%\vlc\vlc.exe". VBShower::Payload (8) is used to install PowerShower. This script creates registry keys to hide the console window and then creates a “MicrosoftAdobeUpdateTaskMachine” scheduler task to execute: powershell.exe -ep bypass -w 01 %APPDATA%\Adobe\AdobeMon.ps1. The decrypted PowerShell script is disguised as a standard module but launches another Base64 encoded script. For VBCloud, a common payload is FileGrabber, which exfiltrates files and documents. The FileGrabber payload ignores Program Files, Program Files (x86), and %SystemRoot% paths. File size for archiving must be between 1,000 and 3,000,000 bytes, and the last modification date must be less than 30 days before the scan.

To read the complete article see: [full article](https://securelist.com/cloud-atlas-h1-2025-campaign/118517/) 

