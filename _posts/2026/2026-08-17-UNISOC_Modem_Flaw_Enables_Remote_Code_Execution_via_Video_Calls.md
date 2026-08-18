---
title: UNISOC Modem Flaw Enables Remote Code Execution via Video Calls
date: 2026-08-17
categories: [SECURITY]
tags: [UNISOC,VULNERABILITY,REMOTE_CODE_EXECUTION,VIDEO_CALLS,ANDROID]
---

## UNISOC Modem Flaw Enables Remote Code Execution via Video Calls

A vulnerability in UNISOC modem firmware can allow arbitrary code execution with kernel privileges from the modem context, potentially allowing an attacker to modify Android kernel code. The flaw stems from a lack of isolation between modem memory and kernel memory. This is according to new research by the SSD Secure Disclosure technical team, credited to independent security researcher 0x50594d. The firm demonstrated a full exploit chain in which modem-level code execution was extended into kernel-level execution.

SSD classified the underlying flaw as **Improper Isolation of Shared Resources** on System-on-a-Chip (SoC), tracked as Common Weakness Enumeration (CWE) 1189. The researchers stated that the missing isolation allows code running in the modem context to access memory used by the Android kernel. This vulnerability allows an attacker who has already gained code execution on the modem to disable protections on a Memory Protection Unit (MPU) region, granting the modem context access to physical memory, including memory used by the Android kernel.

The issue has been identified in phones using UNISOC chipsets, with SSD listing the Xiaomi Redmi A5 with a January 1, 2026 security patch and the Motorola E13 with a February 1, 2025 security patch among affected devices. SSD tested the full chain against a Realme C33 with an Android security update from July 2025. The disclosure links the test to a previously disclosed UNISOC T612 RCE and demonstrates the resulting execution of a payload in kernel space. The final stage was triggered by placing a video call to the target phone. The researchers used a Voice over Long-Term Evolution (VoLTE) connection in their test environment, demonstrating how modem-level execution could be extended to kernel-level code execution.

The disclosure does not identify a vendor firmware update addressing the flaw. SSD also does not present its listed devices as an exhaustive inventory of affected phones. For affected device owners, the disclosure leaves firmware updates from UNISOC and handset manufacturers as the key route to remediation. SSD said it attempted to contact UNISOC through email and LinkedIn. Infosecurity has also contacted UNISOC for comment but has not received a response at the time of writing.

[Read full article](https://www.infosecurity-magazine.com/news/unisoc-modem-flaw-rce-calls/)