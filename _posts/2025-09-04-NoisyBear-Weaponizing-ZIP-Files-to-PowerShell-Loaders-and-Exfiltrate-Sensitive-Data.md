---
title: NoisyBear Weaponizing ZIP Files to PowerShell Loaders and Exfiltrate Sensitive Data
date: 2025-09-04
categories: [CYBERSECURITY]
tags: [NOISYBEAR,ZIP FILES,POWERSHELL,CYBERSECURITY]
---

A sophisticated threat actor known as NoisyBear has emerged as a significant concern for Kazakhstan’s energy sector, employing advanced tactics to infiltrate critical infrastructure through weaponized ZIP files and PowerShell-based attack chains.

The NoisyBear infection chain begins with malicious ZIP files containing three critical components: a decoy document bearing the official KazMunaiGas logo, a README.txt file providing execution instructions, and a weaponized LNK file named “График зарплат.lnk” (Salary Schedule.lnk).

These loaders demonstrate advanced Anti-Malware Scan Interface (AMSI) bypass techniques, using reflection to manipulate the System.Management.Automation.AmsiUtils class. The malware sets the “amsiInitiFailed” flag to convince PowerShell that AMSI initialization has failed, effectively disabling real-time scanning capabilities for subsequent malicious operations.

To read the complete article see: [Cybersecurity News](https://cybersecuritynews.com/noisybear-weaponizing-zip-files/)