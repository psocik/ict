---
title: PolyShell Attacks Target 56% of All Vulnerable Magento Stores
date: 2026-03-25
categories: [SECURITY]
tags: [POLYSHELL,MAGENTO,SECURITY,VULNERABILITIES,ECOMMERCE]
---

## PolyShell Attacks Target Vulnerable Magento Stores 🚨

Attacks leveraging the **PolyShell** vulnerability in version 2 of Magento Open Source and Adobe Commerce installations are underway, targeting more than half of all vulnerable stores. According to eCommerce security company **Sansec**, hackers started exploiting the critical PolyShell issue en masse last week, just two days after public disclosure. 

**"Mass exploitation of PolyShell started on March 19th, and Sansec has now found PolyShell attacks on 56.7% of all vulnerable stores,"** Sansec says. The researchers previously reported that the problem lies in Magento's REST API, which accepts file uploads as part of the custom options for the cart item, allowing polyglot files to achieve remote code execution or account takeover via stored cross-site scripting (XSS), if the web server configuration allows it. 

Adobe released a fix in version 2.4.9-beta1 on March 10, 2026, but it has not yet reached the stable branch. BleepingComputer previously contacted Adobe to ask about when a security update addressing PolyShell will become available for production versions, but we have not received a response.

Sansec reports that in some of the attacks suspected to exploit PolyShell, the threat actor delivers a novel payment card skimmer that uses **Web Real-Time Communication (WebRTC)** to exfiltrate data. WebRTC uses DTLS-encrypted UDP rather than HTTP, so it is more likely to evade security controls even on sites with strict Content Security Policy (CSP) controls like **"connect-src."**

The skimmer is a lightweight JavaScript loader that connects to a hardcoded command-and-control (C2) server via WebRTC, bypassing normal signaling by embedding a forged SDP exchange. It receives a second-stage payload over the encrypted channel, then executes it while bypassing CSP, primarily by reusing an existing script nonce, or falling back to unsafe-eval or direct script injection. Execution is delayed using **'requestIdleCallback'** to reduce detection. 

Sansec noted that this skimmer was detected on the e-commerce website of a car maker valued at over **$100 billion**, which did not respond to their notifications. Additionally, Sansec has published a list of IP addresses that target scanning for web stores vulnerable to PolyShell. The researchers provide a set of indicators of compromise that can help defenders protect against these attacks.

[Read full article](https://www.bleepingcomputer.com/news/security/polyshell-attacks-target-56-percent-of-all-vulnerable-magento-stores/)