---
title: Abusing Paste.ee to Deploy XWorm and AsyncRAT Across Global C2 Infrastructure
date: 2025-06-05
categories: [RESEARCH]
tags: [XWORM,ASYNCRAT,MALWARE,CYBERSECURITY]
---

While reviewing recent malware submissions from a public repository, we flagged a small JavaScript file packed with unusual Unicode characters and broken syntax. At first glance, it looked like malformed or incomplete code, but it was actually a disguised downloader contacting paste.ee, a legitimate service often abused to host staged payloads.

What appeared to be a standalone script turned out to be part of a broader campaign involving obfuscation, paste sites, and globally distributed C2 infrastructure tied to known remote access tools.

Further analysis revealed links to XWorm, a stealthy RAT with capabilities like keystroke logging, data exfiltration, and persistent remote access. In this report, we detail how we traced the activity, extracted IOCs, and built regex and SSL fingerprinting techniques to help defenders detect similar threats.

To read the complete article see:
[Hunt.IO](https://hunt.io/blog/pasteee-xworm-asyncrat-infrastructure)  
