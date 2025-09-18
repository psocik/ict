---
title: China-linked APT41 targets government, think tanks, and academics tied to US-China trade and policy
date: 2025-09-17
categories: [APT]
tags: [APT41,CYBERSECURITY,US-CHINA RELATIONS]
---

Throughout July and August 2025, TA415 conducted spearphishing campaigns targeting United States government, think tank, and academic organizations utilizing U.S.-China economic-themed lures. The report published by Proofpoint states that the group masqueraded as the current Chair of the Select Committee on Strategic Competition between the United States and the Chinese Communist Party (CCP), as well as the US-China Business Council, to target a range of individuals and organizations predominantly focused on U.S.-China relations, trade, and economic policy.  

TA415 runs phishing campaigns that use VS Code Remote Tunnels and legitimate services like Google Sheets and Calendar to gain persistent remote access. By blending with normal traffic, attackers avoid detection. These operations aim to collect intelligence on U.S.-China economic relations amid ongoing trade negotiations, reflecting TA415’s focus on monitoring policy and economic developments.  

The password-protected archive contains an LNK that runs logon.bat from a hidden _MACOS_ folder and shows a corrupt PDF as a decoy. The batch launches an embedded Python loader (WhirlCoil) via pythonw.exe; WhirlCoil installs the VSCode CLI to %LOCALAPPDATA%\Microsoft\VSCode, checks admin rights, and creates a scheduled task to maintain persistence (e.g., GoogleUpdate). The WhirlCoil script runs, saves the verification code, harvests system info and user files, then exfiltrates everything to a free request-logging service. With the verification code, attackers remotely authenticate the VS Code Remote Tunnel to access the host filesystem and terminal.  

U.S. indictments say TA415 operates from Chengdu as Chengdu 404 Network Technology, a private contractor tied to China’s cyberespionage ecosystem. The group worked with other contractors like i-Soon, and some members claimed links to the Ministry of State Security. Proofpoint attributes recent and historical Voldemort backdoor activity to TA415 with high confidence based on infrastructure overlaps, tactics, and targeting that align with Chinese state interests.  

[Read the complete article here.](https://securityaffairs.com/182304/apt/china-linked-apt41-targets-government-think-tanks-and-academics-tied-to-us-china-trade-and-policy.html)  

🔗 For more information, explore open roles at [Team Cymru Careers](https://www.team-cymru.com/careers).