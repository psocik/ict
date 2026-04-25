---
title: BIDI Swap Unmasking the Art of URL Misleading with Bidirectional Text Tricks
date: 2025-07-22
categories: [RESEARCH]
tags: [VULNERABILITY,URL SPOOFING,PHISHING,SECURITY]
---

Varonis Threat Labs is shining a spotlight on a decade-old vulnerability that opens the door to URL spoofing. 

By exploiting how browsers handle Right-to-Left (RTL) and Left-to-Right (LTR) scripts, attackers can craft URLs that appear trustworthy but actually lead somewhere else. Therefore, this method can often be abused in phishing attacks. 

LTR, RTL and BiDi who?  
When it comes to text direction, many languages, like English or Spanish, flow left to right (LTR), while others, such as Arabic or Hebrew, go right to left (RTL). This mix can be a challenge for computers, which need to keep everything aligned so text doesn’t become a scrambled mess. That’s where the Bidirectional (Bidi) Algorithm steps in.  

Part of the Unicode Standard, Bidi helps computers correctly display LTR and RTL scripts in the same text. 

However, while the Bidi Algorithm usually handles domains decently, it struggles with subdomains and URL parameters. This gap means mixed LTR–RTL URLs might not display as intended, creating an open door for mischief. 

To read the complete article see:
[Complete Article](https://www.varonis.com/blog/bidi-swap)