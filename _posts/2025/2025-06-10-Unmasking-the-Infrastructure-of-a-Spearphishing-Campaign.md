---
title: Unmasking the Infrastructure of a Spearphishing Campaign
date: 2025-06-10
categories: [RESEARCH]
tags: [SPEARPHISHING,MALWARE,CYBERSECURITY]
---

**Executive Summary**

A cluster of 16 open directories containing heavily obfuscated Visual Basic Script (VBS) files was discovered, all of which included a filename of "sostener.vbs".

These VBS files form a three-stage obfuscated malware installation system, which ultimately leads to the deployment of a remote access trojan (RATs).

- **Stage 1:** Executes VBScript, decodes a base64 payload, and builds a PowerShell script.
- **Stage 2:** The PowerShell script downloads additional components, including a memory injector and a Remote Access Trojan (RAT).
- **Stage 3:** The Injector loads the final RAT into memory.

Stage 2 loaders often download content from various storage means, such as the Internet Archive (embedded in JPEG images), and text files stored on multiple file hosting services.

Observed RATs include LimeRAT, DCRat, AsyncRAT, and primarily Remcos, the binaries of which are hosted on paste[.]ee or Bitbucket Git repositories.

Command-and-control (C2) infrastructure utilizes "duckdns[.]org" dynamic DNS for rotating IP addresses.

The tactics and language suggest a potential connection to APT-C-36 (Blind Eagle), a Colombian threat actor (however, Censys has no way to confirm this).

To read the complete article see: [Censys Blog](https://censys.com/blog/unmasking-the-infrastructure-of-a-spearphishing-campaign) 😊