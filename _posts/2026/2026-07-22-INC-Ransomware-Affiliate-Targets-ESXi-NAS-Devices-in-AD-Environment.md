---
title: INC Ransomware Affiliate Targets ESXi & NAS Devices in AD Environment
date: 2026-07-22
categories: [CYBERSECURITY]
tags: [RANSOMWARE,ESXI,NAS,AD,CYBERSECURITY]
---

## INC Ransomware Affiliate Targets ESXi & NAS Devices in AD Environment 🚨

Using the Hunt.io platform, Ctrl-Alt-Intel researchers discovered an exposed operator working directory containing evidence of an active ransomware intrusion against a Chinese technology organization. The collection linked cloud-data theft, Active Directory compromise, internal tunneling, attacks against storage and virtualization management planes, and the deployment of an INC encryptor against network-attached storage (NAS). We assess with high confidence that the server belongs to an INC Ransom affiliate. 

The exposed open-directory contained multiple INC ransomware binaries, alongside scripts, tooling, and exfiltrated victim data that can be directly linked to a recent INC Ransom victim - the Chinese company v-silicon.com. More than 50 Python scripts wrapped Microsoft Graph, WinRM, VMware, storage, backup, SSH, and Windows administration interfaces into short, single-purpose workflows. We assess that the affiliate leveraged Large Language Model (LLM) to generate significant amounts of operator tooling that was leveraged in the intrusion.

From the recovered tooling, scripts, artifacts, and exfiltrated data was found on the IP address 213.1[REDACTED BY DNB EDITORS TO GET PAST GOOGLE FILTERS]. From this, we assess the INC Ransom affiliate did the following:
- Access the internal network via GlobalProtect VPN
- Access cloud mail and storage using compromised identities
- Recover network diagrams, administrative guides, asset exports, and credentials
- Use a Windows server as a WinRM-controlled pivot into Active Directory and management networks
- Extract the domain database and registry hives, then target virtualization, backup, and storage platforms
- Create internal forwards to otherwise unreachable management services
- Map NAS shares to the pivot and launch the INC Windows encryptor against each drive.

The affiliate began by turning compromised Microsoft 365 access into infrastructure intelligence. One likely AI-assisted script used the OAuth resource owner password credentials (ROPC) flow to exchange a stolen username and password for a Microsoft Graph token. It then searched the compromised mailbox for operationally useful subjects such as network-circuit relocations, server-room migrations, firewall changes, public IP addresses, VPNs, and internet-service providers. The management-plane targeting was unusually broad.

Scripts granted a compromised identity the global Administrator role in vCenter, attempted to reset appliance and SSO credentials, enabled or checked ESXi remote access, queried backup credentials, and modified NetApp export policies. This targeting is significant because vCenter access concentrates control over large numbers of virtual machines. An affiliate that can modify global permissions, reach ESXi management services, or run Guest Operations against the vCenter Server Appliance can potentially bypass many controls applied to individual workloads.

The affiliate did not need to execute native code on the NAS appliance in order to encrypt its data. Instead, nas_locker.py mapped five SMB shares to drive letters on the compromised Windows pivot and launched the Windows INC encryptor against those mapped drives. The Windows binary was written in Rust and contained functionality for recursive local and network-share encryption, selective fast encryption, process and service termination, shadow-copy removal, and exclusions for selected system and security-software paths. The same archive included payloads for Linux, ESXi, and numerous processor architectures, demonstrating that the affiliate had access to a broader cross-platform impact kit.

[Read full article](https://ctrlaltintel.com/research/INC-Ransom/)