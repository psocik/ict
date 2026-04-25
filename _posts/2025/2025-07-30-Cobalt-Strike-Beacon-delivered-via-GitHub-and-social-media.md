---
title: Cobalt Strike Beacon delivered via GitHub and social media
date: 2025-07-30
categories: [RESEARCH]
tags: [COBALT STRIKE,CYBERSECURITY,MALWARE]
---

In the latter half of 2024, the Russian IT industry, alongside a number of entities in other countries, experienced a notable cyberattack. The attackers employed a range of malicious techniques to trick security systems and remain undetected. To bypass detection, they delivered information about their payload via profiles on both Russian and international social media platforms, as well as other popular sites supporting user-generated content. The samples we analyzed communicated with GitHub, Microsoft Learn Challenge, Quora, and Russian-language social networks. The attackers thus aimed to conceal their activities and establish a complex execution chain for the long-known and widely used Cobalt Strike Beacon.

Although the campaign was most active during November and December 2024, it continued until April 2025. After a two-month silence, our security solutions began detecting attacks again. The adversary employed new malicious samples, which were only slightly modified versions of those described in the article.

Kaspersky solutions detect this threat and assign the following verdicts:
- HEUR:Trojan.Win64.Agent.gen
- HEUR:Trojan.Win64.Kryptik.gen
- HEUR:Trojan.WinLNK.Starter.gen
- MEM:Trojan.Multi.Cobalt.gen
- HEUR:Trojan.Win32.CobaltStrike.gen

To read the complete article see:
[https://securelist.com/cobalt-strike-attacks-using-quora-github-social-media/117085/](https://securelist.com/cobalt-strike-attacks-using-quora-github-social-media/117085/)  

***