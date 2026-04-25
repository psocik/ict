---
title: Qilin EDR Killer Infection Chain
date: 2026-04-02
categories: [MALWARE]
tags: [QILIN,EDR,MALWARE,CYBERSECURITY]
---

## Qilin EDR Killer Infection Chain

This blog post provides an in-depth technical analysis of the malicious dynamic-link library (DLL) **"msimg32.dll"**, which Cisco Talos observed being deployed in Qilin ransomware attacks. This DLL represents the initial stage of a sophisticated, multi-stage infection chain designed to disable local endpoint detection and response (EDR) solutions present on compromised systems. 

The first stage consists of a PE loader responsible for preparing the execution environment for the EDR killer component. This secondary payload is embedded within the loader in an encrypted form.

The loader implements advanced EDR evasion techniques. It neutralizes user-mode hooks and suppresses Event Tracing for Windows (ETW) event generation at runtime by leveraging a -like approach. Additionally, it makes extensive use of structured exception handling (SEH) and vectored exception handling (VEH) to obscure control flow and conceal API invocation patterns. This enables the EDR killer payload to be decrypted, loaded, and executed entirely in memory without triggering detection by the locally installed EDR solution.

During initialization, the loader allocates a heap buffer in process memory that acts as a slot-policy table. The size of this buffer is computed as **"ntdll.dll"** `OptionalHeader.SizeOfCode` divided by 16 ( `SizeOfCode >> 4`), resulting in one byte per 16-byte code slot covering the code region as defined by `OptionalHeader.SizeOfCode` (typically the .text range). Each entry in the table corresponds to a fixed 16-byte block relative to `BaseOfCode`. The loader then iterates over the export table of **"ntdll.dll"**. For each exported function whose name begins with **"Nt"**, the virtual address of the corresponding syscall stub is resolved. From this address, a slot index is calculated as: `slot_idx = (FuncVA - BaseOfCode)/16`. This index is used to mark the corresponding entry in the slot-policy table.

Once active, the EDR killer component loads two helper drivers. The first driver (**"rwdrv.sys"**) provides access to the system's physical memory, while the second driver (**"hlpdrv.sys"**) is used to terminate EDR processes. Prior to loading the second driver, the EDR killer component unregisters monitoring callbacks established by the EDR, ensuring that process termination can proceed without interference. Overall, the malware is capable of disabling over 300 different EDR drivers across a wide range of vendors.

The malicious DLL is most likely side-loaded by a legitimate application that imports functions from **"msimg32.dll"**. To preserve expected functionality, the original API calls are forwarded to the legitimate library located in **"C:\Windows\System32"**.

To read the complete article see:
[Read full article](https://blog.talosintelligence.com/qilin-edr-killer/)