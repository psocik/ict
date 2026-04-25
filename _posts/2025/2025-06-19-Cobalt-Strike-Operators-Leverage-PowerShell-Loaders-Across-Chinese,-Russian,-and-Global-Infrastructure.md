---
title: Cobalt Strike Operators Leverage PowerShell Loaders Across Chinese, Russian, and Global Infrastructure
date: 2025-06-19
categories: [MALWARE]
tags: [COBALT STRIKE,POWERSHELL,CYBERSECURITY,EXPLOITATION]
---

### Key Takeaways

- The PowerShell script (y1.ps1) executes shellcode directly in memory using reflective techniques.
- It connects to a second-stage C2 server hosted on Baidu Cloud Function Compute.
- The shellcode employs API hashing and sets forged User-Agent strings to evade detection.
- The final payload communicates with a known Cobalt Strike IP address in Russia.
- SSL metadata and loader behavior confirm links to Cobalt Strike post-exploitation tools.

To read the complete article see: [Hunt.IO](https://hunt.io/blog/cobaltstrike-powershell-loader-chinese-russian-infrastructure) 
