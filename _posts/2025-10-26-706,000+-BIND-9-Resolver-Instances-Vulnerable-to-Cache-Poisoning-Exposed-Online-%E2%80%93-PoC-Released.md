---
title: 706,000+ BIND 9 Resolver Instances Vulnerable to Cache Poisoning Exposed Online – PoC Released
date: 2025-10-26
categories: [CYBER SECURITY NEWS]
tags: [BIND 9,CACHE POISONING,VULNERABILITY,CVE-2025-40778]
---

A high-severity vulnerability in BIND 9 resolvers has been disclosed, potentially allowing attackers to poison caches and redirect internet traffic to malicious sites. Tracked as CVE-2025-40778, the flaw affects over 706,000 exposed instances worldwide, as identified by internet scanning firm Censys. Assigned a CVSS score of 8.6, this issue stems from BIND’s overly permissive handling of unsolicited resource records in DNS responses, enabling off-path attackers to inject forged data without direct access to the network.

At its core, CVE-2025-40778 exploits a logic flaw in BIND 9’s resolver, where it accepts and caches resource records (RRs) that were not part of the original query. During normal DNS operations, a recursive resolver sends queries to authoritative nameservers and expects responses containing only relevant answers, authority data, and additional sections. However, the affected versions fail to strictly enforce bailiwick principles, which limit records to the queried domain’s authority zone. This leniency allows an attacker to race or spoof responses, injecting fake address records like A or AAAA entries that point to controlled infrastructure.

The vulnerability impacts BIND 9 versions from 9.11.0 through 9.16.50, 9.18.0 to 9.18.39, 9.20.0 to 9.20.13, and 9.21.0 to 9.21.12, including Supported Preview Editions. Earlier versions prior to 9.11.0 are also believed to be vulnerable but unassessed. Only recursive resolver configurations are at risk; authoritative-only servers remain unaffected unless recursion is enabled. Once poisoned, the cache can misdirect downstream clients for hours or days, depending on TTL values, leading to phishing, data interception, or service disruptions without triggering new lookups.

The PoC, published on GitHub by researcher N3mes1s, demonstrates the injection technique using a controlled environment to spoof responses and verify cache poisoning. It highlights how an off-path attacker can monitor query patterns and respond faster than legitimate servers, bypassing traditional protections like source port randomization in some cases. While the code is for educational purposes, security experts warn it could be adapted for real-world use, especially against unpatched systems. To counter CVE-2025-40778, ISC recommends upgrading to patched versions: 9.18.41, 9.20.15, 9.21.14, or later. For those unable to update immediately, restrict recursion to trusted clients via ACLs, enable DNSSEC validation to cryptographically verify responses, and monitor cache contents for anomalies using tools like BIND’s statistics channel.

To read the complete article, visit [Cyber Security News](https://cybersecuritynews.com/bind-9-resolver-instances/).