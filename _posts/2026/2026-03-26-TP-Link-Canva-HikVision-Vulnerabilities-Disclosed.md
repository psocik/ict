---
title: TP-Link, Canva, HikVision Vulnerabilities Disclosed
date: 2026-03-26
categories: [CYBERSECURITY]
tags: [VULNERABILITIES,CYBERSECURITY,TP-LINK,CANVA,HIKVISION]
---

## TP-Link, Canva, HikVision Vulnerabilities Disclosed 🚨

Cisco Talos' Vulnerability Discovery & Research team has recently disclosed critical vulnerabilities affecting **HikVision**, **TP-Link**, and **Canva**. All vulnerabilities have been patched by their respective vendors, in accordance with Cisco's third-party vulnerability disclosure policy.

### Canva Vulnerabilities 🎨
Talos researchers identified **19 vulnerabilities** in **Canva Affinity**, a popular tool for graphic design. Among these, **18** are out-of-bounds read vulnerabilities in the EMF functionality, including:
- **TALOS-2025-2311 (CVE-2025-64776)**
- **TALOS-2025-2310 (CVE-2025-64301)**

These vulnerabilities could allow attackers to exploit specially crafted EMF files, potentially leading to the disclosure of sensitive information. The last vulnerability, **TALOS-2025-2297 (CVE-2025-66342)**, is a type confusion vulnerability that can result in memory corruption and arbitrary code execution.

### TP-Link Vulnerabilities 📶
In addition, **10 vulnerabilities** were found in the **TP-Link Archer AX53** router. Notable vulnerabilities include:
- **TALOS-2025-2290 (CVE-2025-62673)**: Stack-based buffer overflow in the tdpServer ssh port update functionality.
- **TALOS-2025-2283 (CVE-2025-59482)**: Buffer overflow.
- **TALOS-2025-2284 (CVE-2025-62405)**: Stack-based buffer overflow.
- **TALOS-2025-2285 (CVE-2025-59487)**: Write-what-where vulnerability.

These vulnerabilities can be triggered by sending specially crafted network packets, leading to arbitrary code execution.

### HikVision Vulnerability 🛡️
Lastly, a vulnerability was discovered in **HikVision** products:
- **TALOS-2025-2281 (CVE-2025-66176)**: A stack-based buffer overflow vulnerability affecting the SADP XML parsing functionality.

This vulnerability can lead to remote code execution when a malicious packet is sent.

For more detailed information, check out the full article here: [Read full article](https://blog.talosintelligence.com/tp-link-canva-hikvision-vulnerabilities/)