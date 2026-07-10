---
title: New GigaWiper Windows Backdoor Bundles Disk Wiping, Fake Ransomware, and Spyware
date: 2026-07-09
categories: [CYBERSECURITY]
tags: [GIGAWIPER,MALWARE,WINDOWS,RANSOMWARE,SPYWARE]
---

## New GigaWiper Windows Backdoor 🚨

Microsoft has dismantled a destructive Windows backdoor known as **GigaWiper**. What makes it unique is its construction: it combines three older destructive programs into one, allowing operators to choose from various commands. Each command offers a different method to damage a machine:

- **Wipe the entire disk**
- **Overwrite the Windows drive**
- **Run fake "ransomware"** that scrambles files without saving a key.

Interestingly, the same malicious files appear under another name: **BLUERABBIT**, flagged by Binary Defense last month. Microsoft has identified four hashes for the GigaWiper backdoor, which match those listed by Binary Defense for BLUERABBIT, indicating both command servers are the same. This malware is believed to be linked to a group with ties to Iran, targeting Israeli organizations.

### How GigaWiper Operates 🔍

GigaWiper is developed in **Go (Golang)** and operates on Windows. It executes commands that can destroy the machine in different ways:

1. A raw disk wiper that overwrites the physical drive and wipes the partition table.
2. Fake ransomware based on older code called **Crucio**.
3. A wiper targeting the Windows drive, tracked by Microsoft as **FlockWiper**.

For the fake ransomware, there is no ransom note or saved key, meaning there is nothing to pay or decrypt. Once files are encrypted, they cannot be unlocked as the key is lost, and wiped drives can only be restored from clean backups.

### Surveillance Capabilities 👀

The GigaWiper backdoor also has the ability to monitor and control infected PCs. It can:
- Take screenshots of every monitor
- Record the screen while users are active
- Open a hidden VNC session to stream the display and allow attackers to control the mouse and keyboard.

Additionally, it collects system details and can erase Windows event logs to hide its activities. To avoid detection, GigaWiper masquerades as **OneDrive**, creating a scheduled task named **OneDrive Update** that runs every minute. For command traffic, it utilizes legitimate business services instead of standard web requests: **RabbitMQ** for tasking, **Redis** for results, and **MinIO** for data exfiltration.

### Identifying GigaWiper ⚠️

Microsoft has traced the fake ransomware code back to **Crucio** and the multi-pass wiper back to **FlockWiper**, suggesting they were developed by the same individual. The code for Crucio was flagged in a December 2023 CISA advisory regarding **CyberAv3ngers**, a group associated with Iran's Islamic Revolutionary Guard Corps. A recurring tag, **"GRAT"**, appears in both FlockWiper's debug paths and GigaWiper's function names, linking the two tools.

To quickly identify GigaWiper, look for specific signals:
- A **OneDrive Update** scheduled task that repeats every minute
- **RabbitMQ** or **Redis** traffic from regular desktops instead of servers
- Processes using `takeown` and `icacls` to take ownership of Windows boot files like `bootmgr` and `ntoskrnl.exe` outside maintenance windows.

Microsoft recommends enabling tamper protection, blocking known command servers, running endpoint detection in block mode, and activating cloud-delivered protection and automatic remediation.

For more details, check out the full article here: [Read full article](https://thehackernews.com/2026/07/new-gigawiper-windows-backdoor-bundles.html)