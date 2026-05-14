---
title: ClickFix Finds a Backup Plan in PySoxy Proxy Chains
date: 2026-05-13
categories: [CYBERSECURITY]
tags: [CLICKFIX,PYSOXY,CYBERSECURITY,MALWARE]
---

## ClickFix Finds a Backup Plan in PySoxy Proxy Chains 🚀

ReliaQuest has observed attackers pairing **ClickFix** with the **PySoxy** proxy tool to establish redundant encrypted access paths and persistence on compromised systems. ClickFix, a one-shot social engineering technique that tricks victims into executing malicious workflows disguised as fixes to technical issues in their systems, has received a persistence upgrade. In a one-off instance, ReliaQuest researchers spotted an intrusion chain using scheduled tasks, PowerShell-based command-and-control (C2), and a unique abuse of the decade-old open-source proxy tool PySoxy. This campaign was observed in April, marking the first time ReliaQuest had seen ClickFix combined with PySoxy in active intrusions.

The attack commenced with a ClickFix lure that deceived the victim into manually pasting and executing a malicious command disguised as a fix to a technical issue. According to ReliaQuest, the execution flow established persistence through scheduled tasks, conducted domain reconnaissance, and opened an initial PowerShell-based C2 channel back to the attackers. The chain then deployed PyProxy to create a second encrypted communication path, turning the infected endpoint into a proxy relay. As the researchers pointed out in a blog post, PySoxy provides attackers with encrypted proxy access without relying on well-known malware or remote monitoring and management (RMM) tools.

ReliaQuest highlighted that ClickFix is no longer just a social engineering delivery mechanism; it is increasingly being used as a gateway into broader post-exploitation operations involving stealth, persistence, and trusted-tool abuse. The use of PySoxy signifies ClickFix's shift to older legitimate tooling with modular access techniques. By orchestrating multiple communication paths within the chain, attackers are compelling defenders to expand containment efforts. Looking ahead, researchers expect ClickFix operators to continue experimenting with post-exploitation tooling beyond PowerShell. Python is one option, but the underlying logic, using whatever scripting runtime is available to stage proxy or C2 capability without dropping a traditional payload, applies equally to other interpreters.

ReliaQuest advises defenders to specifically investigate recurring scheduled task creation alongside unusual Python-related artifacts and proxy-style command-line activity. Recommendations for incident responders include isolating affected hosts, reviewing scheduled tasks for suspicious re-execution patterns, and hunting for encrypted proxy behavior in Python processes instead of focusing solely on blocked C2 traffic. "Hunt for command lines containing combinations such as -ssl, -remote_ip, -remote_port, SOCKS, or .pyc execution," the researchers stated, adding that these are high-value signals for PySoxy-style activity.

[Read full article](https://www.csoonline.com/article/4170747/clickfix-finds-a-backup-plan-in-pysoxy-proxy-chains.html)