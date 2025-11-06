---
title: Curly COMrades Hacker Group Using New Tools to Create Hidden Remote Access on Compromised Windows 10
date: 2025-11-05
categories: [CYBER SECURITY]
tags: [CURLY COMRADES,REMOTE ACCESS,WINDOWS 10,CYBER SECURITY,MALWARE]
---

By enabling the Hyper-V role and deploying a minimalistic Alpine Linux-based virtual machine, the attackers created a hidden operational environment that hosts custom malware while evading traditional host-based security monitoring.

The virtual machine, requiring only 120MB of disk space and 256MB of memory, provides a dedicated platform for running two custom implants: CurlyShell, a persistent reverse shell, and CurlCat, a reverse proxy tool.

The forensic analysis uncovered that attackers effectively isolated their malware execution environment within a virtual machine, bypassing many traditional security detections by routing malicious traffic through the host’s network stack, making it appear to originate from legitimate IP addresses.

Persistence within the virtual machine operates through a root-level crontab entry that executes every four hours at 20 minutes past the hour. The cron task runs /bin/alpine_init, which subsequently launches the CurlyShell implant located at /bin/init_tools. This custom reverse shell maintains HTTPS communication with the command and control infrastructure, while CurlCat manages SSH reverse proxy tunneling on demand.

To read the complete article see:
[Curly COMrades Hacker Group Using New Tools](https://cybersecuritynews.com/curly-comrades-hacker-group-using-new-tools/) .