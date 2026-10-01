---
title: Global Group Ransomware Abuses WinMerge to Deploy Encryptor
date: 2026-09-30
categories: [CYBERSECURITY]
tags: [RANSOMWARE,MALWARE,CYBERSECURITY,PHISHING]
---

## Global Group Ransomware Abuses WinMerge to Deploy Encryptor

A **Ransomware-as-a-Service (RaaS)** operation known as Global Group is targeting large enterprises with phishing emails that deliver a file-encrypting payload. Research shared by the Cofense Phishing Defense Center (PDC) shows attackers using a fake payment plan, a malicious ISO file, and the legitimate WinMerge application during the infection chain. Cofense describes Global Group as "a rebranding of the legacy Black Lock and Mamona ransomware families," with the operation reusing existing infrastructure and code.

The attack starts with an email posing as a "Suggested Payment Plan" sent from a generic Hotmail address. Its PDF attachment, document_989399.pdf, contains a **Download** button. Clicking it sends the victim to driverupdate.sbs, which prompts them to save an ISO file. The Preview-9dc7.iso file contains Preview-9dc7.exe and a shortcut named Preview-9dc7.pdf.lnk. When the executable runs, it launches WinMerge.exe, a legitimate file-comparison application.

Cofense observed WinMerge connecting to globalsupportupdate.top to retrieve enc.exe, the ransomware encryptor. It is worth noting that WinMerge itself was not compromised. The attackers abused the legitimate application as part of the ransomware delivery process. The encryptor unpacks additional components into C:\Python27.x86, scans local drives, network shares, and databases, and disables security processes before encrypting files. The next step involves encrypted files receiving the nZASJgT extension. The malware changes the desktop wallpaper to display the ransom note and drops README.nZASJgT.txt with payment and file recovery instructions.

According to Cofense's blog post, the ransom note offers decryption keys, technical information about the attack, assistance with cyber insurance claims, and reputation-management services. The operation also uses double extortion, stealing sensitive information and threatening to publish it if the ransom is not paid. Cofense recommends that organizations search for the reported filenames, file extensions, and network indicators to identify potential infections.

[Read full article](https://hackread.com/global-group-ransomware-winmerge-deploy-encryptor/) 
