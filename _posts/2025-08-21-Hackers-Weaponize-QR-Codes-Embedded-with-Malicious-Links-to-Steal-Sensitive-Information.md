---
title: Hackers Weaponize QR Codes Embedded with Malicious Links to Steal Sensitive Information
date: 2025-08-21
categories: [SECURITY]
tags: [QR CODES,CYBER SECURITY,PHISHING]
---

Split QR codes emerged as a stealthier method, dividing a single code into two separate image fragments that appear benign when viewed independently. Email scanners inspecting image attachments typically miss two partial images, yet when rendered in an HTML email they recombine visually into a scannable QR pattern. Victims who scan the composite code are redirected to sites designed to harvest credentials or deploy secondary payloads.

Beyond splitting, the latest quishing kits employ nested QR codes to further obfuscate malicious links. A nested code consists of an inner, benign QR pointing to a harmless URL (e.g., Google), surrounded by an outer code directing to a phishing domain. This dual-layer approach generates ambiguous decoding results: standard QR readers often default to the inner code, while more sophisticated decoders can extract the outer payload. Attackers exploit this ambiguity to bypass QR analysis tools that lack the ability to interpret multiple layers within a single frame.

To read the complete article see: [Cyber Security News](https://cybersecuritynews.com/hackers-weaponize-qr-codes-embedded/) 