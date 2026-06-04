---
title: From Malspam to DesckVB RAT Deployment
date: 2026-06-03
categories: [CYBERSECURITY]
tags: [MALWARE,MALSPAM,RAT,CYBERSECURITY]
---

## From Malspam to DesckVB RAT Deployment 🚨

In May 2026, the Huntress SOC responded to a **DesckVB RAT** infection that began with a malspam. This delivery chain tells an interesting story: the lure routes through **DoubleClick**, a legitimate Google-owned domain that many security tools are less likely to treat as suspicious. The malspam kit personalizes itself on the fly using the victim's email address, dynamically pulling in company branding and location details to make the page feel convincing. This demonstrates how malspam operations are becoming more scalable without becoming less believable.

Once the victim interacts with the lure, the operation shifts to layered malware staging. **DesckVB RAT**, a JavaScript-based Trojan, moves through JScript, PowerShell, and .NET components to retrieve, assemble, and run the final malware in memory. For defenders, the malspam is only the opening move, and everything behind it is built to land quietly, stay hidden, and give the attacker room to operate.

### Initial Access 🚪

Initial access occurred via a malspam email containing a malicious HTML attachment, **Bestellung_2026.html**. This attachment uses a zero-second meta-refresh redirect to a Google DoubleClick Campaign Manager click-tracking URL (ad.doubleclick[.]net). Threat actors route through DoubleClick for filter and reputation evasion, as it is a high-reputation Google-owned domain frequently allowlisted by security gateways. DoubleClick forwards to **fostercareintheus.optimizationprime[.]com/b**, which then leads to the delivery kit at **hxxps://bth.startthewave[.]org/a/**. The lure page dynamically rebrands itself by reading the recipient's email from the URL fragment and rewriting the page title, header logo text, and footer to impersonate the recipient's employer. The company logo is fetched live at runtime via a fallback chain. The kit contains no organization-specific content; swapping the email instantly rebrands it, and prints the viewer's city, region, country, and local time into the header for a personalized and "secure" feel.

### The ZIP Archive 📦

The ZIP archive delivered contains a heavily padded and obfuscated JScript file, **A021185521S210008-11521.js**, a multi-stage loader to retrieve and execute a .NET RAT while evading analysis. The file is heavily padded with junk--hundreds of repeated dead functions, garbage Unicode strings, ;;;;; filler, and Portuguese-language comments. On execution, the script relocates itself to **C:\Users\Public\ktncm.js** if running from a Temp or Downloads folder, then relaunches the copy. The script also holds a large base64 blob mangled with literal A characters and the token 9999 to defeat static detection. This blob is base64-decoded into a PowerShell script, written to **C:\Users\Public\nlbzl.ps1**, and executed hidden. The dropped PowerShell performs a connectivity check and an anti-analysis sweep that enumerates running processes against a blocklist of debugging and sandbox tooling (Dbgview, tcpvcon, Wireshark, OLLYDBG, any.run, sandbox, analyze). If offline or if analysis tools are found, it invokes a function that runs **Restart-Computer -Force**.

### The Builder Script 🛠️

The dropped PowerShell (**nlbzl.ps1**) acts as a builder, assembling a further PowerShell script to **C:\Users\Public\shmvg_01.ps1** for launch. This generated script performs the .NET reflective load (**[Reflection.Assembly]::Load**), resolves the type **ClassLibrary3.Class1**, and invokes the method **prFVI**. The signed Microsoft binary **InstallUtil.exe** is passed as an argument to **prFVI** for signed-binary proxy execution. Two URLs are also passed as arguments to **prFVI**; they are consumed by the final .NET payload. The RAT then phones home to a C2 server, handing the attacker full remote control of the box. The RAT enumerates installed AV products via WMI on the first beacon and specifically detects NVIDIA (GTX/RTX) and AMD (Radeon) GPUs through both WMI and direct registry reads.

To read the complete article see: [Read full article](https://www.huntress.com/blog/malspam-to-deskcvb-rat-delivery-chain-analysis)