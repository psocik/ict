---
title: C2Looper A New Backdoor Likely Tied To Ransomware With GitHub C2
date: 2026-08-17
categories: [CYBERSECURITY]
tags: [MALWARE,RANSOMWARE,C2LOOPER,GITHUB]
---

## C2Looper - A New Backdoor Likely Tied To Ransomware With GitHub C2

In July 2026, Zscaler ThreatLabz identified a new Rust-based malware family that we track as **C2Looper**, which is likely leveraged by a ransomware-related threat actor. Furthermore, ThreatLabz assesses with low to medium confidence that C2Looper has been delivered to victims through a multi-stage ClickFix infection chain. C2Looper supports typical backdoor commands including remote shell execution, reconnaissance, and deploying additional malware tooling. Additionally, C2Looper dynamically resolves Windows APIs and encrypts strings.

C2Looper uses plaintext HTTP to communicate with its C2 server through a simple network protocol. C2Looper collects host information and sends it to the C2 server as a JSON object in an HTTP POST request. This JSON object contains the username, DNS hostname of the compromised host, the process identifier (PID) of C2Looper, and a Bot ID which is a combination of the username and hostname. C2Looper sends this information to the endpoint `/api/beacon` every second to request a command. Interestingly, Oyster malware (which is likely related to the threat actor behind Lactrodectus) uses similar API endpoints for C2 communication.

C2Looper appears to be under active development. During our research, ThreatLabz identified a new version of C2Looper that supports additional commands, and most interestingly, uses GitHub for C2 communication. We also observed that the older C2Looper variant described previously was used to download the latest version of C2Looper through the upload command. This latest version appears to be internally tagged as version 2. C2Looper v2 uses GitHub for all C2 operations, including storing exfiltrated data and reporting command output. The binary includes debug messages including '!!! v2 !!! pongv2 from'. This is used as a response when the network command ping is used. This is an indicator that the malware developer refers to this variant as version 2 of C2Looper. Since this variant uses GitHub for C2 communication, the endpoints have been removed. Instead, C2Looper creates a directory for each bot in the GitHub repository and uses specific JSON files.

Overall, C2Looper is a new malware family that provides common backdoor capabilities, including system command execution and deploying arbitrary second-stage binaries. This functionality is likely used by an initial access broker to steal sensitive data and deploy ransomware. Despite its code simplicity, the additional functionality in the latest variant indicates that its developers continue to expand and refine their capabilities.

[Read full article](https://www.zscaler.com/blogs/security-research/c2looper-new-backdoor-likely-tied-ransomware-github-c2)