---
title: VerdantBamboo Just Another BRICKSTORM in the Firewall
date: 2026-06-04
categories: [CYBERSECURITY]
tags: [VERDANTBAMBOO,BRICKSTORM,MALWARE,CYBERSECURITY]
---

## VerdantBamboo: Just Another BRICKSTORM in the Firewall 🚀

In September 2025, Volexity conducted an incident response engagement after suspicious network traffic was observed from a Linux-based virtual machine appliance on a customer's network. This virtual machine was an Egnyte Storage Sync system. Volexity discovered that instead of connecting to a domain affiliated with Egnyte, the appliance was connecting to a threat-actor-controlled domain behind Cloudflare IP addresses.

Ultimately, Volexity's analysis revealed that a Chinese threat actor, tracked as VerdantBamboo (WARP PANDA, UNC5221), had compromised the Storage Sync system. The suspicious connections observed were the result of a malware implant known as **BRICKSTORM**. The initial findings determined that the threat actor used the malware's proxying capabilities deployed on the Storage Sync system, along with compromised credentials, to access the victim's Microsoft 365 (M365) environment. Further investigation uncovered a much longer timeline: the initial compromise had actually occurred at least 18 months earlier.

After Volexity completed the initial remediation effort, VerdantBamboo returned to breach the victim organization again by connecting with stolen administrative credentials to the victim's firewall. VerdantBamboo used that access to enable and configure web SSL VPN access to that device, which was then used to connect to internal systems and deploy additional custom malware to a Synology NAS appliance.

During the investigation, Volexity determined that VerdantBamboo had compromised the victim organization's Managed Services Provider (MSP). A brief investigation of the MSP's network revealed that the MSP's pfSense firewall had also been compromised by VerdantBamboo with a BSD variant of BRICKSTORM. Volexity concluded that this firewall, like the victim organization's Storage Sync system, had also been compromised at least 18 months earlier. Volexity assesses with medium confidence that the victim organization had been compromised through VerdantBamboo's breach of the MSP.

Forensic investigation of the Storage Sync system and the pfSense firewall resulted in the discovery of multiple samples of the BRICKSTORM backdoor.

While BRICKSTORM was the primary implant used by VerdantBamboo, Volexity identified two previously undocumented malware families: **PLENET**, a malware family written in .NET Core, and **AGENTPSD**, a malware family written in Python. Volexity assesses with high confidence that AGENTPSD served as a fallback should VerdantBamboo's primary backdoor no longer function.

Volexity's investigation determined that VerdantBamboo was able to access the Storage Sync system using valid credentials via secure shell (SSH) with an unprivileged account named `egnyteservice`. Evidence showed that VerdantBamboo discovered the settings for the account's sudo configuration, which included an inadvertent local privilege escalation.

According to the system logs, VerdantBamboo created a file in `/etc/cron.d/` named `ssync` that would execute `/home/egnyteservice/ssync.sh`. After this operation was successful, the threat actor removed the file from `/etc/cron.d`, meaning there was no long-term persistence method for this implant.

[Read full article](https://www.volexity.com/blog/2026/06/04/verdantbamboo-just-another-brickstorm-in-the-firewall/)