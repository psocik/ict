---
title: WantToCry Ransomware Evades Detection Through SMB Abuse
date: 2026-05-20
categories: [CYBERSECURITY]
tags: [RANSOMWARE,SMB,CYBERSECURITY,WANTTOCRY]
---

## WantToCry Ransomware Evades Detection 🚨

Attacks using **WantToCry ransomware** are targeting exposed Server Message Block (SMB) ports and utilizing remote encryption to minimize the chance of detection, Sophos reported on Tuesday. WantToCry ransomware, not to be confused with WannaCry, has been around since at least early 2024, as indicated by a February 2024 PCrisk guide covering the WantToCry strain. Files encrypted by WantToCry have the ".want_to_cry" extension, and attackers leave behind a ransom note titled "!want_to_cry.txt".

### Key Findings 🔍

Research by the Sophos Counter Threat Unit Research Team found that WantToCry targets victims by scanning for SMB services exposed to the internet on ports 139 and 445. A January 2026 scan using Shodan revealed more than **1.5 million exposed SMB ports**, most of which were located in the United States (more than 600,000 ports), Sophos said. Attackers initiate authenticated SMB sessions via brute-forcing attempts or using compromised credentials, and subsequently use these sessions to exfiltrate files for remote encryption. Files are encrypted on the attacker's server, rather than on the victim's machine, limiting the chance of detection as no malware is executed in the victim's environment. After remote encryption, the encrypted files are written back to their original locations using the same SMB sessions, according to Sophos.

### Ransom Demands 💰

WantToCry's ransom demands are significantly lower than many major ransomware groups, ranging from **$300 to $1,800 in Bitcoin**. Ransom notes instruct victims to make contact via qTox or Telegram, where they are offered the decryption of three small files for free as evidence that decryption is possible. Although WantToCry exfiltrates files via SMB, there is no evidence that these files are used for extortion, as seen in typical double-extortion ransomware schemes. Sophos traced WantToCry's infrastructure to several different IP addresses: one IP address associated with a Russian hosting provider was used for reconnaissance and brute-force attempts, while six other IP addresses spread out across Russia, Germany, the United States, and Singapore were observed using authenticated SMB sessions for file writes and exfiltration.

### Identified Computer Names 🖥️

Two computer names used by attackers -- a Windows Server 2016 device named **WIN-J9D866ESIJ2** and a Windows Server 2019 device named **WIN-LIVFRVQFMKO** -- were also identified by Sophos. The WIN-J9D866ESIJ2 was previously reported by Team Cymru to be involved in attacks deploying NetSupport RAT in 2025. Additionally, WIN-LIVFRVQFMKO has been associated with attacks linked to LockBit, Qilin, and ALPHV/BlackCat ransomware, based on research by Sophos and third-party researchers. 

### Recommendations 📊

Sophos noted that while WantToCry does not deploy ransomware locally, its activity can still be detected via network and authentication artifacts. The researchers said organizations should monitor for unusual SMB read and write operations from external IP addresses and block inbound SMB traffic from ports TCP/139 and TCP/445 when possible. They also recommend disabling the outdated SMBv1 protocol and any "guest" or anonymous SMB access.

For more detailed information, you can read the full article [here](https://www.scmagazine.com/news/wanttocry-ransomware-evades-detection-through-smb-abuse-remote-encryption).