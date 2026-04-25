---
title: Like burglars closing a door, Apache ActiveMQ attackers patch critical vuln after breaking in
date: 2025-08-19
categories: [VULNERABILITIES]
tags: [APACHE ACTIVEMQ,VULNERABILITY,CYBERSECURITY]
---

Criminals exploiting a critical vulnerability in open source Apache ActiveMQ middleware are fixing the flaw that allowed them access, after establishing persistence on Linux servers.

Researchers at security house Red Canary observed attackers using a new form of Linux malware, dubbed DripDropper, against dozens of systems running Apache's Java-based message broker. The miscreants got in using CVE-2023-46604, a CVSS 9.8 critical flaw that Apache itself rates as a perfect 10. After installing a backdoor to the infected systems, they then downloaded two Java Archive (JAR) files that effectively patched the original vuln.

"This kind of behavior is very uncommon, we see it very rarely," Brian Donohue, principal researcher at Red Canary, told The Register. "I think we've only seen it once before and it's not something that happens very often. Most threats are pretty much point and play and don't often include this sort of really customized trick."

To read the complete article see: [The Register](https://www.theregister.com/2025/08/19/apache_activemq_patch_malware/).