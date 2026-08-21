---
title: BTR Reforged Weaponizing Defender's Remediation Driver as a Kernel Operation Primitive
date: 2026-08-20
categories: [RESEARCH]
tags: [BTR,DEFENDER,REMEDIATION,KERNEL,SECURITY]
---

## BTR Reforged: Weaponizing Defender's Remediation Driver as a Kernel Operation Primitive

What if a **signed Microsoft remediation driver** could be instructed to execute arbitrary **file** and **registry** operations from **Ring 0** - **without** exploits, vulnerabilities, or memory corruption? In this publication, we present the first full reverse engineering of the **Windows Defender Boot-Time Removal driver** (`BTR.sys`) and its proprietary transaction format. We dissect its encrypted configuration mechanism, integrity validation logic, and execution pipeline, and demonstrate how this legitimate remediation component can be transformed into a **universal kernel operation** engine. We introduce `BTR_CLI`, a **research tool** that constructs valid encrypted transactions and safely exercises the driver's functionality to demonstrate its capabilities. Furthermore, we demonstrate how `BTR_CLI` can be used as an **EDR/AV** bypass technique, disarming security solutions while using a **trusted Windows built-in**, **Microsoft-signed** driver, thus **not relying** on typical **BYOVD** techniques. 🚀

This research originated during an incident response investigation involving a compromised system, where certain endpoint telemetry appeared suspicious but was ultimately traced back to legitimate Windows Defender remediation activity. During analysis, a driver (internally identified as `BTR.sys`) appeared on disk under `System32\drivers` with a randomized filename and a corresponding randomized service name (`HKLM\SYSTEM\CurrentControlSet\Services\mzqnjtaq`), accompanied by the following registry entries: `Type` (REG_DWORD, 1: Kernel Driver), `Start` (REG_DWORD, 1: System Start), `ErrorControl` (REG_DWORD, 0: Ignore), `ImagePath` (REG_EXPAND_SZ, `\\??\\C:\Windows\system32\drivers\mzqnjtaq.sys`), `Group` (REG_SZ, `Boot Bus Extender`), and `Args` (REG_SZ, `C:\Windows\system32\drivers\mzqnjtaq.sys:changelist`). 

At first glance, several characteristics resembled attacker tradecraft: A randomly named driver dropped shortly before reboot, creation of a transient service entry for loading it, presence of RC4 encryption routines, interaction with an Alternate Data Stream (`:changelist`) attached to the driver file, and self-cleanup behavior after execution. These indicators strongly resembled malicious kernel loader behavior, particularly given prior research into exotic loading mechanisms such as loading kernel drivers directly from ADS paths - a technique often considered theoretical yet has proven practical. 

Our research reveals how trusted security infrastructure can unintentionally expose powerful primitives, what this means for defenders, and how **similar patterns** may exist in **other signed remediation** components. This work blends reverse engineering, kernel internals, and detection engineering into a practical case study of **when defensive technology becomes offensive capability**. 

To read the complete article see: [Read full article](https://research.checkpoint.com/2026/btr-reforged-weaponizing-defenders-remediation-driver-as-a-kernel-operation-primitive/)