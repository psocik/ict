---
title: Cracking ValleyRAT From Builder Secrets to Kernel Rootkits
date: 2025-12-10
categories: [RESEARCH]
tags: [VALLEYRAT,CYBERSECURITY,ROOTKITS,CHECK POINT RESEARCH]
---

The "Driver Plugin" contains an embedded kernel-mode rootkit that, in some cases, retains valid signatures and remains loadable on fully updated Windows 11 systems, bypassing built-in protection features. Through detailed reverse engineering, previously unknown capabilities were uncovered, including stealthy driver installation, user-mode shellcode injection via APCs, and forceful deletion of AV/EDR drivers.

Another notable observation is that among the detected samples, we found 30 distinct variants of the ValleyRAT builder and 12 variants of the rootkit driver. The majority of the detected rootkits were compiled in 2025, based on PE compilation timestamps that appeared intact. Seven of the drivers were still signed with valid (non-revoked) certificates. Despite all certificates being expired long ago (validity periods ending before 2015), they fall under the driver signing policy exceptions for end-entity certificates issued before July 29th 2015 that chain to a supported cross-signed CA. We confirmed that several of these drivers were not properly detected by Microsoft Defender Antivirus, were absent from the latest version of the Microsoft Vulnerable Driver Blocklist, and could still be loaded on fully updated Windows 11 systems with all protection features enabled (including HVCI and Secure Boot). We responsibly disclosed these findings to the Microsoft Security Intelligence team.

In addition to the "Normal Mode" of the driver installation described above, the client can also trigger "Stealth Mode". In that case, the function is supplemented by additional routines. This mode primarily aims to disrupt network connectivity during installation and use MalSeclogon-based impersonation to reduce detection likelihood. To disrupt network connectivity, the client launches various commands, and the MalSeclogon technique is used to execute these commands under an impersonated context with PPID spoofing.

We introduce a custom low-level re-implementation of file deletion using direct kernel IRP calls. It operates as follows: Opens files via a custom IRP_MJ_CREATE, Resets attributes via IRP_MJ_SET_INFORMATION, Marks files for deletion, and Temporarily detaches section objects to bypass file locks, including memory-mapped executables. It is triggered automatically during driver initialization and via IOCTL from the user-mode client.

To read the complete article see: [Check Point Research](https://research.checkpoint.com/2025/cracking-valleyrat-from-builder-secrets-to-kernel-rootkits/).