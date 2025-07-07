---
title: Unmasking Insecure HTTP Data Leaks in Popular Chrome Extensions
date: 2025-07-05
categories: [RESEARCH]
tags: [CHROME EXTENSIONS,SECURITY,DATA LEAKS]
---

Extensions analyzed expose information such as browsing domains, machine IDs, OS details, usage analytics, and more.  
Many users assume that popular Chrome extensions adhere to strong security practices, especially when the extensions themselves promise functionality related to privacy, ranking analytics, or convenient new tab features. However, recent findings show that several widely used extensions—SEMRush Rank, PI Rank, MSN New Tab/Homepage, DualSafe Password Manager, and Browsec VPN—unintentionally transmit sensitive data over simple HTTP. By doing so, they expose browsing domains, machine IDs, operating system details, usage analytics, and even uninstall information, in plaintext. Because the traffic is unencrypted, a Man-in-the-Middle (MITM) attacker on the same network can intercept and, in some cases, even modify this data, leading to far more dangerous scenarios than simple eavesdropping. This blog illustrates the exact points where these leaks occur, why they are problematic, and how the resulting disclosures can be exploited for profiling, data correlation, or targeted attacks.  

To read the complete article see: [Read More](https://www.security.com/threat-intelligence/chrome-extension-leaks)  
