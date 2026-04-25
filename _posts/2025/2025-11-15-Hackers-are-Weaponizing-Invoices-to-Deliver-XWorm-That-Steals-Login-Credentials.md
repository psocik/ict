---
title: Hackers are Weaponizing Invoices to Deliver XWorm That Steals Login Credentials
date: 2025-11-15
categories: [MALWARE]
tags: [CYBER SECURITY,XWORM,MALWARE,RAT]
---

Attackers are using fake invoice emails to spread XWorm, a remote-access trojan that quietly steals login credentials, passwords, and sensitive files from infected computers. The script immediately drops a batch file named IrisBud.bat into the Windows temporary folder and uses Windows Management Instrumentation to execute it invisibly. The initial .vbs file contains 429 lines of heavily disguised code that writes another file to the system. This batch file then copies itself to the user profile directory under the name aoc.bat, ensuring persistence even if the temporary files get cleaned up. The PowerShell script performs the final stage of the attack by reading the hidden payloads from aoc.bat, decrypting them using AES encryption with a hardcoded key, and decompressing the data with GZip. This produces two executable files that load directly into memory without ever being saved to disk, a technique called fileless execution that helps avoid detection by traditional antivirus software.

To read the complete article see: [here](https://cybersecuritynews.com/hackers-are-weaponizing-invoices-to-deliver-xworm/) 