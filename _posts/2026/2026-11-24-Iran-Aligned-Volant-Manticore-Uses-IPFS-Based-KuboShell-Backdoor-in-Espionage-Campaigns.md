---
title: Iran-Aligned Volant Manticore Uses IPFS-Based KuboShell Backdoor in Espionage Campaigns
date: 2026-11-24
categories: [CYBERSECURITY]
tags: [IRAN,CYBER ESPIONAGE,KUBO SHELL,VOLANT MANTICORE,IPFS]
---

## Iran-Aligned Volant Manticore Uses IPFS-Based KuboShell Backdoor in Espionage Campaigns

A previously undocumented Iran-aligned cyber espionage group called **Volant Manticore** has targeted telecommunications companies, airlines, and critical infrastructure in Cyprus. Central to the group's operations is a backdoor called **KuboShell** that uses the **InterPlanetary File System (IPFS)** for command-and-control (C2) and deploys **Homa**, a post-compromise framework that's a reimplementation of MuddyWater's MuddyC2Go. Both MuddyWater and Volant Manticore are assessed to be affiliated with Iran's Ministry of Intelligence and Security (MOIS). 

> "While we identified multiple links to MuddyWater, we assess that Volant Manticore likely consists of former MuddyWater operators who branched off from the group and currently operate as a separate threat cluster," Check Point said in an analysis published today.

### Attack Chains and Phishing Campaigns

Attack chains have been found to leverage **artificial intelligence (AI)**-generated personas in bogus CVs to trick targets into clicking on a link to download the complete resume, resulting in the deployment of KuboShell on the victim's system. The activity is said to have been aimed at a Cyprus-based airline that operates flights between Cyprus and Israel. As recently as **September 2026**, the group has been found to launch a phishing campaign against Saudi targets, distributing the backdoor and N-able RMM through two different healthcare-themed ZIP archives named **"AI_Healthcare_Seminar.zip"** and **"Ai_Healthcare_Seminar_Online.zip,"** respectively.

### Technical Details of KuboShell

Regarding technical details, a Windows backdoor, KuboShell, uses IPFS for C2 and relies on **Pinata** to facilitate file transfer over the peer-to-peer (P2P) file-sharing network. KuboShell retrieves the MAC address of the machine's first network adapter and uses it as a unique identifier for each victim. Analysis indicates that KuboShell is primarily used to run basic reconnaissance commands and assess the compromised environment before downloading and executing a more capable backdoor, which includes the modular **Homa Framework**.

### The Homa Framework Process

The modular Homa Framework involves a three-stage process:
- **PowerShell Stager**: Contacts a hard-coded IP address ("185.205.187[.]109:8000") to fetch a PowerShell loader and execute it in memory.
- **PowerShell Loader**: Decodes and launches a JavaScript backdoor.
- **JavaScript Backdoor**: Implements a continuous C2 loop to receive and execute PowerShell, SSH, and "cmd.exe" commands.

> "We assess that Homa's client is a JavaScript reimplementation of the older MuddyC2Go client, potentially allowing Volant Manticore to retain the more complex server-side component with minimal modifications, thereby reducing development time and resources," Check Point said.

### Conclusion

In conclusion, **Volant Manticore** shows how Iran's cyber ecosystem continues to reshape itself. If MuddyC2Go is the latest MuddyWater framework Volant Manticore's operators had access to, the split may have happened around **2023** as MuddyWater replaced MuddyC2Go with DarkBeatC2 in late 2023.

[Read full article](https://thehackernews.com/2026/11/iran-aligned-volant-manticore-uses-ipfs.html)