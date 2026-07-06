---
title: Unpatched Flaws Disclosed in Filesystem Bundled Into Millions of Embedded Devices
date: 2026-07-03
categories: [SECURITY]
tags: [VULNERABILITIES,EMBEDDED-DEVICES,SECURITY,FATFS]
---

## Unpatched Flaws Disclosed in Filesystem Bundled Into Millions of Embedded Devices

🚨 **Security Alert!** Security firm runZero has disclosed **seven vulnerabilities** in **FatFs**, a small filesystem library that allows devices to read and write FAT and exFAT formats used on USB drives and SD cards. These flaws are critical because FatFs is ubiquitous, found in the firmware of security cameras, drones, industrial controllers, hardware crypto wallets, and other devices built on real-time operating systems.

### The Risks

On the worst-affected systems, an attacker can exploit these vulnerabilities by using a booby-trapped USB drive, SD card, or update file, potentially corrupting memory and executing their own code. Many embedded devices lack the memory protections found on phones and desktops, leading runZero to state that "any physical access leads to a jailbreak."

### Vulnerabilities Overview

All seven bugs operate similarly: the device attempts to read a malformed storage volume or firmware image, causing FatFs to mishandle the bad data. runZero rated these vulnerabilities as **Medium to High** severity, with no Criticals. The most concerning bug is **CVE-2026-6682** (CVSS 7.6), which involves an integer overflow in the code that mounts a FAT32 volume, potentially leading to memory corruption and code execution.

Other notable vulnerabilities include:
- **CVE-2026-6687** (7.6, High): An exFAT volume-label field overflow that allows attackers to gain a foothold for memory corruption.
- **CVE-2026-6683** (4.6, Medium): An exFAT divide-by-zero error that can crash the device and potentially brick hardware during an update.

### The Challenge of Fixing

Fixing these issues is challenging as FatFs is maintained by a single developer. runZero has attempted to contact the maintainer and involved Japan's JPCERT/CC coordination center, but has received no response. Currently, there is no upstream fix for the memory-corruption bugs, no security mailing list, and no way for the many products that bundle FatFs to determine if they are affected.

### Affected Platforms

Affected platforms include:
- Espressif ESP-IDF
- STMicroelectronics STM32Cube
- Zephyr
- MicroPython
- ArduPilot
- RT-Thread
- Mbed
- Samsung TizenRT
- SWUpdate updater

This issue extends into consumer IoT, industrial gear, drones, and crypto wallets. As of runZero's July 1 disclosure, no attacks exploiting these bugs have been reported, but the exploit material is already public. runZero has provided proof-of-concept disk images, a test harness, and a working QEMU-based exploit example in a companion repository.

### Recommendations

For those developing firmware that interacts with FAT or exFAT media, the advice is clear: **Audit your code!** Locate the copy of FatFs in your product, review the wrapper code, scrutinize how you handle filenames and file sizes, and prepare to patch.

[Read full article](https://thehackernews.com/2026/07/unpatched-flaws-disclosed-in-filesystem.html)