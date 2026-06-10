---
title: BLUERABBIT A Golang-Based Backdoor with Ransomware and Destructive Capabilities
date: 2026-06-09
categories: [CYBERSECURITY]
tags: [MALWARE,BACKDOOR,RANSOMWARE,CYBERSECURITY]
---

## BLUERABBIT - A Golang-Based Backdoor with Ransomware and Destructive Capabilities 🚨

A full-featured backdoor with file encryption, drive wiping, and a C2 channel that resembles normal message broker traffic, **BLUERABBIT** is a Golang-based backdoor attributed to a likely Iran-nexus threat actor. It routes its command-and-control through RabbitMQ (AMQP) for tasking, Redis for state management, and MinIO for S3-compatible data exfiltration. BLUERABBIT is a full-spectrum intrusion tool, offering remote access, system profiling, file encryption with a .candy extension, and two distinct disk-wiping modules capable of rendering systems permanently unrecoverable.

### Key Features:
- **First Observed:** Mid-to-late March 2026
- **Target:** Entities in Israel
- **Related Activity:** Linked to the same likely Iran-nexus activity cluster that previously leveraged BLUEWIPE and SEWERGOO in June 2025.

The combination of exfiltration and encryption is consistent with a double extortion model: data is stolen before encryption occurs. Upon execution, BLUERABBIT checks the registry key `HKCU\Software\OneDrive\Environment` to track its execution count. If this key does not exist, the malware assumes it is running for the first time and executes a PowerShell command to establish persistence as a scheduled task named "OneDrive Update," deliberately impersonating a legitimate Microsoft service. The task is configured with two triggers: one that fires five seconds after registration with a one-minute repeat interval, and one at system startup. Because the task repeats every 60 seconds with automatic restart on failure, simply killing the BLUERABBIT process is insufficient. The scheduled task itself must be removed to break persistence.

BLUERABBIT's main execution loop follows the sequence **MessageReader**, **ProcessTask**, **UpdateRedis**, relying on enterprise messaging and database protocols rather than conventional HTTP-based C2. When launching the VNC remote desktop module, BLUERABBIT creates a firewall rule under the deceptive name **Microsoft.Windows.CloudExperienceHost** to blend in with legitimate Windows components. Prior to executing destructive actions, BLUERABBIT uses `takeown` and `icacls` to take ownership of and grant full access to critical boot files, including `bootmgr`, `ntoskrnl.exe`, and `winload`. The following registry modifications are made to disable automatic reboot and system recovery. Collectively, these modifications ensure that once BLUERABBIT begins encryption or wiping, the system cannot automatically recover, reboot into repair mode, or interrupt the destructive process.

### Detection Opportunities:
Several characteristics of BLUERABBIT create reliable detection opportunities. Non-hex GUID directories are a key signal: BLUERABBIT's staging directories use the full alphanumeric range (A-Z, 0-9) in a GUID-formatted path. Legitimate Windows GUIDs are strictly hexadecimal. A scheduled task named "OneDrive Update," created via `New-ScheduledTaskAction` with `AllowStartIfOnBatteries`, `Hidden`, and an immediate start trigger, is distinctive. Additionally, externally routed AMQP traffic on endpoint devices is a high-fidelity detection signal. Any process running `takeown` or `icacls` against `bootmgr`, `ntoskrnl.exe`, or `winload.efi/winload.exe` outside of a sanctioned patching window should trigger an immediate alert.

### Indicators of Compromise:
- **File SHA-256:** 633d4cbd496b1094495da89a64f5e6c31a0f6d4d1488411db5b0cba1cfe42001
- **IP Address:** [REDACTED BY DNB EDITORS FOR GOOGLE FILTERS]

To read the complete article see:
[Read full article](https://binarydefense.com/resources/blog/bluerabbit-a-golang-based-backdoor-with-ransomware-and-destructive-capabilities) 
