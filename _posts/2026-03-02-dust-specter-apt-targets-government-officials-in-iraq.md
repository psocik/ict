---
title: Dust Specter APT Targets Government Officials in Iraq
date: 2026-03-02
categories: [CYBERSECURITY]
tags: [APT,IRAQ,MALWARE,CYBERSECURITY]
---

## Dust Specter APT Targets Government Officials in Iraq 🚨

In January 2026, Zscaler ThreatLabz observed activity by a suspected Iran-nexus threat actor targeting government officials in Iraq. ThreatLabz discovered previously undocumented malware including **SPLITDROP**, **TWINTASK**, **TWINTALK**, and **GHOSTFORM**. Due to significant overlap in tools, techniques, and procedures (TTPs), as well as victimology, ThreatLabz assesses with medium-to-high confidence that an Iran-nexus threat actor conducted this operation. ThreatLabz tracks this group internally as **Dust Specter**.

This campaign targeted government officials in Iraq by impersonating Iraq’s Ministry of Foreign Affairs, and Iraq government–related infrastructure was compromised and used to host malicious payloads distributed as part of this campaign.

### Attack Chains and Malware Development 🛠️

ThreatLabz observed several fingerprints in the codebase indicating that Dust Specter leveraged generative AI for malware development. They identified two attack chains with different previously undocumented malware tooling:

1. **Attack Chain 1** includes **SPLITDROP**, a .NET-based dropper that drops **TWINTASK** and **TWINTALK** to continue the next stage of the attack.
2. **Attack Chain 2** uses **GHOSTFORM**, a .NET-based RAT that consolidates all the functionality of the first attack chain into one binary and uses in-memory PowerShell script execution.

**GHOSTFORM** employs creative evasion techniques such as invisible Windows forms along with timers to delay its own execution.

### Delivery Method 📦

Attack Chain 1 is delivered in a password-protected RAR archive named `mofa-Network-code.rar`. The password for this archive is: `92,110-135_118-128`. A 32-bit .NET binary, disguised as a WinRAR application, is present inside this archive and starts the attack chain on the endpoint. This binary functions as a dropper and ThreatLabz named it **SPLITDROP** because it drops two modules that we named **TWINTASK** and **TWINTALK**.

Upon being launched, **SPLITDROP** displays a dialog box prompting the victim to enter a password to extract an archive file. Before decrypting the resource, **SPLITDROP** displays a message box stating, “The download did not complete successfully,” to distract the victim while it operates in the background.

### Malicious Components 🦠

Upon being launched, **VLC.exe** sideloads the malicious DLL **libvlc.dll** which was extracted alongside **VLC.exe** in the same directory by **SPLITDROP**. ThreatLabz named this malicious component **TWINTASK**. **TWINTASK** functions as a worker module, and its main purpose is to poll a file for new commands available for execution and run them using PowerShell.

Persistence is established via a Windows registry entry under `HKCU:\Software\Microsoft\Windows\CurrentVersion\Run` for **VLC.exe**. Additionally, **WingetUI.exe** sideloads the malicious DLL **hostfxr.dll**, which ThreatLabz named **TWINTALK**. **TWINTALK** is a 32-bit .NET DLL and functions as a C2 orchestrator whose main purpose is to poll the C2 server for new commands, coordinate with the worker module, and exfiltrate the results of command execution to the C2 server.

**TWINTALK** deserializes a cleartext JSON object returned by the server to extract C2 commands, parsing fields by position rather than by JSON key name. The server was observed randomizing JSON key names on each response, an evasion method intended to evade pattern-matching–based detection used by network security.

To read the complete article see: [Read full article](https://www.zscaler.com/blogs/security-research/dust-specter-apt-targets-government-officials-iraq)