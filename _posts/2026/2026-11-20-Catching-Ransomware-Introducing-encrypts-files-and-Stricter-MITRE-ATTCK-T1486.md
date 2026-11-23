---
title: Catching Ransomware Introducing encrypts-files and Stricter MITRE ATT&CK T1486
date: 2026-11-20
categories: [CYBERSECURITY]
tags: [RANSOMWARE,MALWARE,CYBERSECURITY,VIRUS,THREAT-INTELLIGENCE]
---

## Catching Ransomware: Introducing encrypts-files and Stricter MITRE ATT&CK T1486

When investigating ransomware, the key question is often: **Did this file actually encrypt user documents when executed?** This week, we rolled out three updates across VirusTotal and Google Threat Intelligence to identify malware that encrypts user files. 

### New Features 🚀
- A new `encrypts-files` Tag Across Windows and macOS Sandboxes provides a cipher-agnostic behavioral trait (`behaviour_tags:encrypts_files`) and file-level search tag (`tag:encrypts-files`), emitted only when dynamic analysis confirms real encryption of user documents.
- Stricter MITRE ATT&CK `T1486` Gating in CAPE Sandbox now requires verified user-file encryption before emitting `T1486` mappings, reducing false positives across platform-wide `T1486` volume by **97.6%** (from 7,238 to 171 files per day) and cutting CAPE-only daily `T1486` hits from 1,039/day to 0 on benign files.

### Verification Gates 🔒
Across CAPE Sandbox (Windows), Zenbox (Windows), and macOS Mirage (Apple Silicon), our sandboxes apply verification gates before emitting `encrypts-files`. Content Destruction and Entropy Verification (Cipher-Agnostic) inspects modified user-file content on disk using format-aware verification, evaluating destroyed file structures, elevated entropy, or non-text byte patterns. This catches AES, ChaCha20, intermittent encryption, and XOR ciphers alike.

### Real-World Impact 🌍
Across 328,257 newly submitted unique files analyzed since November 17, `tag:encrypts-files` matched 55 files, surfacing in-the-wild and validation payloads across diverse file types and architectures with zero benign software false positives. For example, in an active `.k404` extortion campaign, Python locker `fb0982bb9f5d5700685dcf4e99ff695f4593fbc3e3d0359d4c2baf23c545f354` (`system_update.pyw`) was flagged by 0 out of 75 static antivirus engines at the time of analysis. When detonated in Zenbox, it rewrites Desktop user files into `.k404` ciphertext, setting both `tag:encrypts-files` and `T1486`.

### Conclusion 📝
`tag:encrypts-files` is a high-precision confirmation signal, not an exhaustive recall filter; a missing tag does not mean a sample is benign or lacks ransomware logic. Automated sandbox runs will not emit the tag in several common scenarios, such as samples that require command-line arguments or passwords, sandbox evasion, user-interaction gates, long sleeps, or when unreachable command-and-control key servers are involved. Security teams can use `tag:encrypts-files` (or `behaviour_tags:encrypts_files`) immediately across VirusTotal Intelligence Search and the v3 REST API to streamline workflows. This includes Building Clean Ransomware Validation Corpora for EDR and Storage Defense, providing fresh samples guaranteed to perform real disk-level file encryption when testing ransomware rollback and anomaly-detection sensors.

[Read full article](https://blog.virustotal.com/2026/11/catching-ransomware-introducing.html)