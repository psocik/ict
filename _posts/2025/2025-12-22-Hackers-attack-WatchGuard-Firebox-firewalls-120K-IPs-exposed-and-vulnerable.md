---
title: Hackers attack WatchGuard Firebox firewalls 120K IPs exposed and vulnerable
date: 2025-12-22
categories: [SECURITY]
tags: [WATCHGUARD,FIREBOX,VULNERABILITY,CYBERSECURITY]
---

With hackers already knocking at the gates, around 120,000 WatchGuard Firebox firewalls, which protect thousands of companies, remain unpatched and vulnerable to a critical flaw, according to the latest research by the ShadowServer Foundation.

“An out-of-bounds Write vulnerability in the WatchGuard Fireware OS IKED (IKE daemon) process may allow a remote unauthenticated attacker to execute arbitrary code. This vulnerability affects both the mobile user VPN with IKEv2 and the branch office VPN using IKEv2 when configured with a dynamic gateway peer,” the vendor explains in an advisory.

Threat actors have been actively attempting to exploit this vulnerability in the wild. WatchGuard listed four IP addresses directly associated with the attacks. Attackers use them to both probe for vulnerable devices, make exploitation attempts, and command and control.

“During a successful exploit, the IKED process (responsible for handling IKE negotiations) will hang, interrupting VPN tunnel negotiations and re-keys. This is a strong indicator of attack,” the vendor warned.

To read the complete article see: [https://cybernews.com/security/critical-security-risk-affects-120k-watchguard-fireboxes/](https://cybernews.com/security/critical-security-risk-affects-120k-watchguard-fireboxes/) 
