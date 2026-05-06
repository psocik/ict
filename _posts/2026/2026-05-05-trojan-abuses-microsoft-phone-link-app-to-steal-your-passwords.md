---
title: Trojan Abuses Microsoft Phone Link App to Steal Your Passwords
date: 2026-05-05
categories: [CYBERSECURITY]
tags: [TROJAN,MALWARE,MICROSOFT,SECURITY]
---

## 🚨 Trojan Abuses Microsoft Phone Link App to Steal Your Passwords

Cisco Talos researchers have revealed the exploits of a Remote Access Trojan (RAT) that can steal your credentials the moment you launch the Microsoft Phone Link app to connect your phone to your PC. Microsoft Phone Link is an app that comes preinstalled on Windows 10 and 11, allowing users to connect their phone to a Windows PC via Bluetooth and Wi-Fi.

CloudZ is a modular Remote Access Trojan (RAT), compiled as a .NET executable and equipped with a range of defenses against analysis and reverse engineering, including obfuscation and the detection of debuggers and profilers in its environment. The malware loads its instructions into memory during execution, establishes a connection to a command-and-control (C2) server, and executes PowerShell scripts to extract, download, and exfiltrate data to the attacker-controlled C2 server. If CloudZ has infected a Windows PC, the Trojan can spy on these systems using the newly discovered 'Pheno' plugin, which is a malicious module designed to monitor and scan for active Phone Link processes. Once CloudZ is alerted to an active connection through Pheno's surveillance capabilities, the Trojan attempts to hijack and intercept the Phone Link application's SQLite database file.

If successful, CloudZ can steal sensitive information as it passes from the smartphone to the PC, including credentials, SMS messages, and potentially one-time passcodes (OTPs). This Trojan abuses legitimate Windows functions rather than exploiting an application vulnerability, a common practice among many surveillance- and data-theft-focused malware strains. Cisco Talos' latest research highlights how cross-device syncing attacks can occur to bypass modern security controls, such as two-factor authentication (2FA) and OTP delivery. While Cisco Talos researchers aren't sure of the initial attack vector, when the malware landed on a Windows PC, it executed as a fake ScreenConnect application update, which then deployed the RAT.

Trojans are often spread disguised as legitimate software, downloaded from social media, via phishing links, or found on warez websites. You should only ever download software from official sources, and even then, enable real-time file scanning through your antivirus program or app to detect suspicious files. Trojans and associated malware are also often included in bundles of pirated software. Unless the software is licensed, you are putting your PC at risk, and these kinds of RATs could lurk on your system undetected for a long time before they trigger and steal your data.

[Read full article](https://www.zdnet.com/article/trojan-abuses-microsoft-phone-link-app-to-steal-passwords/)