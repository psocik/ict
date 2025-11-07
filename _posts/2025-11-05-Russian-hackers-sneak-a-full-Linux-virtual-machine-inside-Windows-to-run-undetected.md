---
title: Russian hackers sneak a full Linux virtual machine inside Windows to run undetected
date: 2025-11-05
categories: [APT]
tags: [CYBERSECURITY,WINDOWS,LINUX,MALWARE]
---

Russian hackers are exploiting Microsoft’s Hyper-V virtualization feature to create a hidden Linux virtual machine within a target’s host, allowing them to covertly install secret implants on the victim's computer.

A Russia-linked threat actor, dubbed Curly COMrades, was caught enabling Hyper-V on victim systems, spinning a minimalistic Alpine Linux-based virtual machine (VM) that consumes only 120MB of disk space and 256MB of RAM, running in parallel with Windows. The hackers then use this VM to host a suite of malicious tools that remain undetected by Windows defenses.

Later, they deployed the VM and configured it to run custom malicious implants, CurlyShell and CurlCat, for reverse shell and reverse proxy operations. The hackers configured the VM to use the host’s IP address (Default Switch network adaptor). In effect, all malicious outbound communication appears to originate from the legitimate host machine's IP address.

To read the complete article see: [Russian hackers sneak a full Linux virtual machine inside Windows to run undetected](https://cybernews.com/security/russian-hackers-abuse-microsoft-hyperv-to-run-linux/).