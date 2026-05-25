---
title: Cloud Atlas Targets Russian and Belarusian Public Sector with New Tools
date: 2026-05-22
categories: [CYBERSECURITY]
tags: [CLOUD ATLAS,RUSSIA,BELARUS,CYBER ATTACKS,MALWARE]
---

## Cloud Atlas Attacks the Public Sector and Diplomatic Structures

In 2025, we observed pervasive SSH tunnel activity, which has remained active into 2026, affecting many government organizations and commercial companies in Russia and Belarus. Behind some of this activity is **Cloud Atlas**, a group we have known since 2014. During our investigation, we identified new tools used by this group, as well as indicators of compromise. The group is back to sending out archives containing malicious shortcuts that launch PowerShell scripts. We have observed the use of third-party public utilities like Tor, SSH, and RevSocks for persistence in infected systems and to create additional backup control channels.

### Primary Compromise
As for the primary compromise, Cloud Atlas remains consistent in using phishing. In observed campaigns, attackers emailed a ZIP archive containing an LNK file as an attachment, using these shortcuts to covertly execute PowerShell scripts hosted on external resources. The PowerShell script downloaded performs several actions: drops `$temp\fixed.ps1`, creates a 'Run' registry key for persistence, downloads and extracts a decoy PDF, opens the PDF for user distraction, and then executes `$temp\fixed.ps1`. The primary purpose of the Fixed.ps1 script is to deliver and install subsequent malware onto the compromised system, specifically **VBCloud** and **PowerShower**.

### VBCloud and PowerShower
The VBCloud module functions as a dropper for the VBCloud backdoor, dropping `video.vbs` and `video.mds`. VBCloud::Backdoor connects to a C2 server to receive additional scripts or execute built-in commands, designed to function as a stealer, targeting files with extensions of interest such as DOC, PDF, XLS, and exfiltrating them. Unlike VBCloud, PowerShower is primarily used for network reconnaissance and lateral movement within the victim's infrastructure. PowerShower can collect information about running processes, administrator groups, and domain controllers, download and execute PowerShell scripts from the C2 server, and conduct 'Kerberoasting' attacks. PowerShower downloads an additional script for stealing credentials, which creates a Volume Shadow Copy of the C:\ drive and copies the SAM and SECURITY system files from this shadow copy to C:\Users\Public\Documents\, disguising them as PDF files. The script uses a UAC bypass technique via `fodhelper.exe` to execute with high privileges.

### Lateral Movement
Moving laterally across the victim's network, attackers executed a PowerShell script named `rdp_new.ps1`, designed to allow multiple RDP sessions in Windows 10 by patching the `termsrv.dll` file. The patched version allows multiple concurrent logins so attackers can stay connected without disrupting the legitimate user, thereby reducing suspicion. Adversaries widely deployed reverse SSH tunnels, installed via VBS scripts, to many hosts of interest, achieving persistence via a new scheduled task. Some OpenSSH binaries used had their imports modified, replacing `libcrypto.dll` with `syruntime.dll`. Additionally, the attackers installed RevSocks, an alternative Go-lang tool for tunnels and proxy connections. They also utilized Tor tunneling to maintain control, making the infected machine accessible via RDP from the Tor network.

### New Tool: PowerCloud
Finally, we analyzed a new Cloud Atlas tool, **PowerCloud**, which collects user data with administrator privileges and writes this information to Google Sheets in Base64 format.

[Read full article](https://securelist.com/cloud-atlas-2026/119895/)