---
title: Critical U-Boot Bugs Undermine Secure Boot on Millions of Devices
date: 2026-07-11
categories: [SECURITY]
tags: [UBOOT,VULNERABILITIES,SECURITY,BOOTLOADER]
---

## Critical U-Boot Bugs Undermine Secure Boot on Millions of Devices

Binarly's research team has discovered **six vulnerabilities** in U-Boot, the open-source bootloader that powers home routers, smart cameras, server management controllers, and a significant portion of the embedded hardware that drives the internet. All six vulnerabilities are triggered during the verification of a FIT image, which is the format U-Boot uses to package and validate the software it loads. 

### Key Findings
- **Two vulnerabilities** can lead to arbitrary code execution.
- **Four vulnerabilities** can trigger a denial-of-service condition.

The affected code has been present in U-Boot since version v2013.07, meaning over **50 stable releases** are potentially impacted. U-Boot is critical because it runs before the operating system and any security software. As stated in the report by Binarly, "Because U-Boot is one of the first components to run during the boot process, it is highly security-sensitive: severe flaws at this stage can be used by a potential attacker to compromise everything that is loaded and executed afterwards." Malicious code planted at this stage is extremely difficult to detect and nearly impossible to remove without physically reflashing the device's storage chip.

### Vulnerability Details
Binarly focused on the **FIT Signature Verification** component specifically because breaking it would undermine the entire concept of verified boot. 
- **BRLY-2026-037** stems from a function called `fdt_find_regions`, where a function can return NULL in certain cases, and the code never checks for this. An attacker controlling memory address 0x0 can exploit this NULL dereference into a stack-based buffer overflow.
- **BRLY-2026-038** builds on the same root cause but exploits a different consequence, causing a stack buffer underflow.
- **BRLY-2026-039** allows an attacker to set the declared string size to 0xFFFFFFFF, crashing the bootloader.
- **BRLY-2026-040** is another null pointer dereference that crashes U-Boot on any platform where the zero page is unmapped.
- **BRLY-2026-041** involves FIT images with externally stored payload data, enabling attackers to crash the bootloader by pointing the data region outside mapped memory.
- **BRLY-2026-042** triggers during FIT format validation due to deep nesting, causing stack exhaustion regardless of the device's RAM.

### Recommendations
A reasonable assumption is that exploiting a bootloader vulnerability requires physical access to the hardware. However, Binarly counters this by referencing earlier research on Supermicro BMC firmware, indicating that any device accepting firmware updates over a network may be reachable without physical access. All six patches have been accepted upstream and are available in U-Boot's master branch. Organizations running devices built on U-Boot, particularly server hardware with BMC controllers, should apply the patches through their vendor's firmware update process as soon as updates become available. 

For more details, you can read the full article [here](https://securityaffairs.com/195150/security/critical-u-boot-bugs-undermine-secure-boot-on-millions-of-devices.html).