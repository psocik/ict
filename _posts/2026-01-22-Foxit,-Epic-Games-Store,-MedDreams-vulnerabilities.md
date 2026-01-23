---
title: Foxit, Epic Games Store, MedDreams vulnerabilities
date: 2026-01-22
categories: [VULNERABILITIES]
tags: [FOXIT,EPIC GAMES STORE,MEDDREAMS,VULNERABILITIES,CISCO TALOS]
---

Cisco Talos’ Vulnerability Discovery & Research team recently disclosed three vulnerabilities in Foxit PDF Editor, one in the Epic Games Store, and twenty-one in MedDream PACS. The vulnerabilities mentioned in this blog post have been patched by their respective vendors, all in adherence to Cisco’s third-party vulnerability disclosure policy.

For Snort coverage that can detect the exploitation of these vulnerabilities, download the latest rule sets from Snort.org.

### Foxit PDF Editor Vulnerabilities
Foxit PDF Editor, a popular PDF handling platform, was found to have three vulnerabilities by KPC of Cisco Talos. 
- **TALOS-2025-2275 (CVE-2025-57779)** is a privilege escalation vulnerability in the installation of Foxit PDF Editor via the Microsoft Store. A low-privilege user can replace files during the installation process, which may result in elevation of privileges.
- **TALOS-2025-2277 (CVE-2025-58085)** and **TALOS-2025-2278 (CVE-2025-59488)** are use-after-free vulnerabilities, one in the way Foxit Reader handles a Barcode field object, and one in the way Foxit Reader handles a Text Widget field object. A specially crafted JavaScript code inside a malicious PDF document can trigger these vulnerabilities, which can lead to memory corruption and result in arbitrary code execution. An attacker needs to trick the user into opening the malicious file to trigger these vulnerabilities. Exploitation is also possible if a user visits a specially crafted, malicious site if the browser plugin extension is enabled.

### Epic Games Store Vulnerability
KPC of Cisco Talos also discovered **TALOS-2025-2279 (CVE-2025-61973)**, a local privilege escalation vulnerability in the installation of Epic Games Store via the Microsoft Store. For this Epic Games Store vulnerability, a low-privilege user can replace a DLL file during the installation process, which may result in elevation of privileges.

### MedDream PACS Vulnerabilities
In addition, Marcin “Icewall” Noga of Cisco Talos discovered 21 reflected cross-site scripting (XSS) vulnerabilities across several functions of MedDream PACS Premium 7.3.6.870. MedDream PACS server is a medical-integration system for archiving and communicating about DICOM 3.0 compliant images. An attacker can provide a specially crafted URL to trigger these vulnerabilities, which can lead to arbitrary JavaScript code execution. **These include:**
- **TALOS-2025-2253 (CVE-2025-54817)**: autoPurge functionality  
- **TALOS-2025-2254 (CVE-2025-53516)**: downloadZip functionality  
- **TALOS-2025-2255 (CVE-2025-54495)**: emailfailedjob functionality  
- **TALOS-2025-2256 (CVE-2025-54157)**: encapsulatedDoc functionality  
- **TALOS-2025-2257 (CVE-2025-54778)**: existingUser functionality  
- **TALOS-2025-2271 (CVE-2025-58087-CVE-2025-58095)**: config.php functionality  

To read the complete article see: [Foxit and Epic Games](https://blog.talosintelligence.com/foxi-and-epic-games/)  
