---
title: WinRAR Flaw Could Allow Attackers to Take Control of Your Computer
date: 2026-07-02
categories: [CYBERSECURITY]
tags: [WINRAR,VULNERABILITY,CYBERSECURITY,MALWARE]
---

## WinRAR Vulnerability Alert 🚨

Rarlab has released a new version of the popular WinRAR tool to patch a vulnerability that can be abused in remote code execution attacks. The issue is fixed in **WinRAR 7.23**, but users must install the new version manually because WinRAR still does not offer automatic updates. They also need to ensure they download the version that matches their system and language preference. There are five operating systems to choose from: **Windows, macOS, Android, Linux, and FreeBSD**. More people may struggle with choosing between **64 bits, 32 bits, or ARM**, which requires checking their system specifications.

The vulnerability, tracked as **CVE-2026-14191**, affects the way WinRAR and UnRAR handle RAR5 recovery-volume (.rev) files, which are optional files used to help repair damaged or incomplete archives. This means an attacker can craft a set of two or more .rev files that make WinRAR write data outside the memory it has allocated. In simple terms, the malicious recovery volumes can trick WinRAR into writing data just past the end of a memory buffer, corrupting its own data, which attackers may exploit to run malicious code on the victim's computer. According to the **European Vulnerability Database** entry **EUVDB-2026-40869**, the bug is a variant of the 2023 flaw tracked as **CVE-2023-40477**, which was also found in the recovery volume handling code.

The problem with the lack of automatic updates is that users first have to become aware that a new version is available. Although there are third-party tools that can monitor this for system administrators, most home users risk missing it. A 2025 vulnerability in WinRAR was exploited by Russia-aligned groups against Ukrainian organizations long after the vulnerability had been patched.

To stay safe, besides installing the updated version of WinRAR and/or UnRAR, additional general ways include:
- **Don't open unsolicited attachments** unless you can verify their origin through an independent channel.
- **Use an up-to-date, real-time anti-malware solution** to keep malware off your devices.
- For system administrators, it is recommended to treat WinRAR as optional software. If users do not need it for business reasons, remove it through your software inventory or asset management system to shrink the attack surface, or use a suitable tool to notify you promptly about updates.

For more details, check out the full article here: [Read full article](https://www.malwarebytes.com/blog/news/2026/07/winrar-flaw-could-allow-attackers-to-take-control-of-your-computer)