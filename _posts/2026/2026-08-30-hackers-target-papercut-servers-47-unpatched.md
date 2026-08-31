---
title: Hackers Target PaperCut Servers 47% Unpatched
date: 2026-08-30
categories: [CYBERSECURITY]
tags: [HACKERS,PAPERCUT,VULNERABILITY,CYBERSECURITY,REMOTE-CODE-EXECUTION]
---

## Hackers Target PaperCut Servers: 47% Unpatched

🚨 **Attention all PaperCut users!** 

PaperCut servers are currently under active attack, with **47%** of tracked installations still running unpatched versions vulnerable to remote code execution. The print management software, widely used in schools, hospitals, and offices globally, confirmed on **August 27** that a pre-authentication remote code execution flaw is being actively exploited against real customers.

Researchers at **Huntress** have discovered evidence of exploitation in two customer environments and successfully reproduced the entire attack chain against a clean, unpatched install. They reported that the observed activity focused on system discovery, resembling reconnaissance rather than a finished operation, which usually precedes something more severe.

### What’s the Vulnerability?

The vulnerability stems from a simple authorization mistake in PaperCut. An attacker can send a specially crafted request that makes the server display one page while executing an action from another. This flaw, tracked as **CVE-2026-81578**, allows attackers to change the server's configuration without logging in. Combined with another flaw, **CVE-2026-82078**, attackers can run arbitrary Java code on the server, leading to code execution at the highest Windows privilege level.

### Real-World Attacks

The attacks observed by Huntress were surprisingly basic, with one incident lasting under two minutes. The attacker executed simple commands to identify the compromised account and Windows version. Investigators found a malicious Java class file dropped directly into PaperCut's installation directory, capable of running commands and deleting logs to cover its tracks. A Derby database log entry remained, indicating a high-confidence compromise.

### Patching Process

PaperCut's patching process is complex. The company released an emergency patch, followed by another update less than 24 hours later. The bigger concern is that about **47%** of the roughly **2,500** PaperCut installations tracked still run version **23** or earlier, which currently have no patch available. 

If your organization runs one of these older versions, the safest option is to remove the PaperCut Application Server from the public internet and restrict access through a VPN or trusted internal network until a proper fix is available. Before restarting the server, save its logs and configuration files, and check for any unexpected files in the server's lib directory. Even a brief reconnaissance attempt could indicate a more serious attack.

For more details, [Read full article](https://securityaffairs.com/198107/uncategorized/hackers-are-probing-papercut-servers-and-47-still-have-no-patch.html)!