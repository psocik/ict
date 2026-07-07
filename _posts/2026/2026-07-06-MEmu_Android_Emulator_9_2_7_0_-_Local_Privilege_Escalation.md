---
title: MEmu Android Emulator 9.2.7.0 - Local Privilege Escalation
date: 2026-07-06
categories: [SECURITY]
tags: [ANDROID,EMULATOR,VULNERABILITY,PRIVILEGE_ESCALATION]
---

## MEmu Android Emulator 9.2.7.0 - Local Privilege Escalation 🚨

A Local Privilege Escalation (LPE) vulnerability, **CVE-2026-36213**, has been identified in MEmu Android Emulator 9.2.7.0. The vulnerability was publicly disclosed on **June 16, 2026** by exploit author Mohammad and affects MEmu Android Emulator version 9.2.7.0, tested on Windows 10 x64 and Windows 11 x64.

MEmu Android Emulator 9.2.7.0 installs a Windows service named **"MEmuSVC"** that runs with **NT AUTHORITY\SYSTEM** (LocalSystem) privileges. The service binary, located at `C:\Program Files\Microvirt\MEmu\MemuService.exe`, is installed with insecure NTFS permissions. These permissions grant **FullControl (F)** to low-privileged groups, specifically **BUILTIN\Users** and **Everyone**. A low-privileged local user can replace the service binary with a malicious executable. Upon service restart, the malicious binary executes with **NT AUTHORITY\SYSTEM** privileges. This vulnerability is classified as **Incorrect Access Control**, **CWE-732** (Incorrect Permission Assignment for Critical Resource), and carries a **CVSS v3.1 Score of 7.8 HIGH**.

### Verification
To verify this vulnerability, users can run the command: `icacls "C:\Program Files\Microvirt\MEmu\MemuService.exe"`. Vulnerable output would display permissions such as: `C:\Program Files\Microvirt\MEmu\MemuService.exe BUILTIN\Users:(F) Everyone:(F) NT AUTHORITY\SYSTEM:(F) BUILTIN\Administrators:(F)`.

The Proof of Concept (PoC) for **CVE-2026-36213** outlines the attack flow. It first verifies vulnerable permissions on the **TARGET_BINARY**, `C:\Program Files\Microvirt\MEmu\MemuService.exe`. If the target is vulnerable, a malicious payload is created, and the service binary is replaced. Subsequently, the **TARGET_SERVICE**, **"MEmuSVC"**, is restarted. The payload should then execute as **SYSTEM**. The PoC explicitly notes: **"[!] Run this as a LOW-PRIVILEGED user! [!] This PoC demonstrates LPE."**

### Disclosure Timeline
- **Discovered:** February 20, 2026
- **CVE Assigned:** February 20, 2026
- **Vendor Notified:** June 11, 2026
- **Public Disclosure:** June 16, 2026

For more details, check the [Read full article](https://www.exploit-db.com/exploits/52615).