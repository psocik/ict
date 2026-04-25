---
title: Vidar Stealer 2.0 adds multi-threaded data theft, better evasion
date: 2025-10-21
categories: [MALWARE]
tags: []
---

According to an announcement from the developer this month, Vidar 2.0 has been rewritten in C, supports multi-threading data stealing, bypasses Chrome's app-bound encryption, and features more advanced evasion mechanisms.

"The malware also employs an advanced technique that launches browsers with debugging enabled and injects malicious code directly into running browser processes using either shellcode or reflective DLL injection," explains Trend Micro.

"The injected payload extracts encryption keys directly from browser memory, then communicates the stolen keys back to the main malware process via named pipes to avoid disk artifacts."

"This approach can bypass Chrome's AppBound encryption protections by stealing keys from active memory rather than attempting to decrypt them from storage." Campaigns are projected through Q4 2025 as the "malware's technical capabilities, proven developer track record since 2018, and competitive pricing position it as a likely successor to Lumma Stealer's dominant market position."

To read the complete article see: [Bleeping Computer](https://www.bleepingcomputer.com/news/security/vidar-stealer-20-adds-multi-threaded-data-theft-better-evasion/).