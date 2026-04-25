---
title: JSFireTruck Exploring Malicious JavaScript Using JSF*ck as an Obfuscation Technique
date: 2025-06-12
categories: [MALWARE]
tags: [MALICIOUS JAVASCRIPT,JSFIRETRUCK,OBFUSCATION,CYBERSECURITY]
---

### Executive Summary

We recently discovered a large-scale campaign that has been compromising legitimate websites with injected, obfuscated JavaScript code. Threat actors commonly use this type of campaign to invisibly redirect victims from legitimate websites to malicious pages that serve malware, exploits, and spam.

The campaign uses a JavaScript obfuscation technique known as JSF*ck (profanity masked). Due to the profanity in the term, we refer to the method in the remainder of this article by using the nickname JSFireTruck.

#### Key Findings:
- Multiple websites have been identified with injected malicious JavaScript that uses JSFireTruck obfuscation, which is composed primarily of the symbols `[]+${}`.
- The code's obfuscation hides its true purpose, hindering analysis.
- The injected code checks the website referrer, and if the referrer is a search engine, the code redirects victims to malicious URLs.
- Retroactive hunting on VirusTotal and our internal telemetry revealed thousands of related samples, indicating this is a widespread infection campaign affecting many websites.
- Injected JavaScript will redirect users to websites that can lead to malware downloads or other harmful activities, like malvertising and traffic monetization.

The campaign's scale and stealth pose a significant threat. The widespread nature of these infections suggests a coordinated effort to compromise legitimate websites as attack vectors for further malicious activities.

To read the complete article see: [JSFireTruck Article](https://unit42.paloaltonetworks.com/malicious-javascript-using-jsfiretruck-as-obfuscation/) 
