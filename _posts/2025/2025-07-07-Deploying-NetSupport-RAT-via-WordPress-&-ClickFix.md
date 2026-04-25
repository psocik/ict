---
title: Deploying NetSupport RAT via WordPress & ClickFix
date: 2025-07-07
categories: [RESEARCH]
tags: [CYBERSECURITY,PHISHING,MALWARE]
---

**Source:** Cybereason  

### Excerpt:  
**Delivery Mechanism**  
Threat actors utilize phishing campaigns to distribute a malicious website link through:  
- Phishing emails  
- PDF attachments  
- Gaming websites  

**Attack Flow**  
1. **Website Compromise:** Malicious script injects iframe on compromised site on victims’ access.  
2. **DOM Manipulation:** The threat actor manipulates the Document Object Model (DOM) to display a fake CAPTCHA page.  
3. **Payload Delivery:** Users, following the fake CAPTCHA instructions, download the NetSupport RAT.  
4. **Post-Infection:** The threat actor connects to the NetSupport Client process and performs reconnaissance using the NetSupport Remote Command Prompt.  

To read the complete article see:  
[NetSupport RAT via WordPress & ClickFix](https://www.cybereason.com/blog/net-support-rat-wordpress-clickfix) 