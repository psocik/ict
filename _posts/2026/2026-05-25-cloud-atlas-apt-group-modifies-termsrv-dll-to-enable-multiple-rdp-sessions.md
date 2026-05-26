---
title: Cloud Atlas APT Group Modifies termsrv.dll to Enable Multiple RDP Sessions
date: 2026-05-25
categories: [CYBERSECURITY]
tags: [CLOUD,APT,CYBERSECURITY,RDP,THREAT]
---

## Cloud Atlas APT Group Modifies termsrv.dll to Enable Multiple RDP Sessions

A well-known advanced persistent threat group called **Cloud Atlas** has been caught using a dangerous technique to hijack Windows systems without alerting anyone on the network. The group modifies a core Windows file called `termsrv.dll` to unlock multiple simultaneous Remote Desktop Protocol (RDP) sessions on a victim's computer. This lets attackers work in the background while a legitimate user stays logged in, making detection much harder for security teams. 🚨

Cloud Atlas has been active since at least 2014, and over the past year, the group ramped up attacks against government agencies and diplomatic organizations, particularly in Russia and Belarus. Researchers at Securelist identified this latest wave of activity, noting the group's toolkit expanded significantly in the second half of 2025 and into early 2026. According to Securelist, the attackers target state institutions and diplomatic bodies, using new and established techniques to maintain persistent access inside compromised networks.

### Attack Methodology
The initial entry point in most cases was a phishing email carrying a ZIP archive with a malicious shortcut file. When a victim opens the shortcut, it quietly runs a PowerShell script pulled from an external server. That script sets up persistence, downloads a decoy PDF to distract the user, removes infection traces, and deploys payloads including a backdoor called **VBCloud** and a reconnaissance tool called **PowerShower**. Once inside a network, the group moves laterally and executes the `termsrv.dll` modification. This lets them maintain access without forcing any existing user offline, reducing the chance anyone notices something is wrong.

### Key Weapon
The key weapon in this campaign is a PowerShell script named `rdp_new.ps1` that directly modifies `termsrv.dll` in Windows 10. `termsrv.dll` controls how the Remote Desktop service behaves, and by default, Windows limits the system to a single concurrent RDP session. The script takes ownership of `termsrv.dll`, grants itself full access rights, and replaces a specific byte sequence to remove the single-session restriction. After the patch is applied, the RDP service restarts and the change takes effect. This technique is dangerous because it targets a trusted Windows system file rather than an obviously suspicious third-party tool. Standard monitoring may not flag changes to an existing system DLL, giving attackers a wide window to operate inside an infected host without raising alarms.

### Additional Tactics
Additionally, Cloud Atlas layers its access by deploying reverse SSH tunnels alongside the RDP manipulation. A compromised machine initiates an outbound SSH connection to an attacker-controlled server, bypassing most firewall rules that block incoming connections. To keep tunnels running, the group uses VBS scripts executed through **PAExec** or **PsExec** and schedules them as Windows tasks for automatic restarting. These layered channels mean removing one access method does not guarantee the attackers are fully evicted.

### Mitigation Strategies
To mitigate this threat, security teams should monitor for unexpected changes to `termsrv.dll`, review Windows Firewall modifications, and audit scheduled tasks for unfamiliar VBS or PowerShell entries. Watching for unusual outbound SSH connections and blocking known malicious domains at the network perimeter are also critical steps in reducing exposure to this ongoing threat. 🔒

[Read full article](https://cybersecuritynews.com/cloud-atlas-apt-group-modifies-termsrv-dll/)