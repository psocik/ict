---
title: AVEVA Process Optimization
date: 2026-01-15
categories: [VULNS]
tags: [AVEVA,PROCESS OPTIMIZATION,ICS-CERT,VULNERABILITIES,CVE-2025]
---

**Title**: AVEVA Process Optimization  
**Source**: ICS-CERT Advisories  
**Date Published**: January 15, 2026  

Successful exploitation of these vulnerabilities could enable an attacker to execute remote code, perform SQL injection, escalate privileges, or access sensitive information. The following versions of AVEVA Process Optimization are affected: Process Optimization (CVE-2025-61937, CVE-2025-64691, CVE-2025-61943, CVE-2025-65118, CVE-2025-64729, CVE-2025-65117, CVE-2025-64769). These critical vulnerabilities impact Critical Manufacturing sectors worldwide, affecting AVEVA Process Optimization versions <=2024.1.  

Specifically, CVE-2025-61937, if exploited, could allow an unauthenticated miscreant to achieve remote code execution under OS System privileges of "taoimr" service, potentially resulting in complete compromise of the Model Application Server. This is categorized as CWE-94 Improper Control of Generation of Code ('Code Injection'). Additionally, CVE-2025-61943 could allow an authenticated miscreant (Process Optimization Standard User) to tamper with queries in Captive Historian and achieve code execution under SQL Server administrative privileges, potentially resulting in complete compromise of the SQL Server (CWE-89 Improper Neutralization of Special Elements used in an SQL Command ('SQL Injection')). Another critical flaw, CVE-2025-65118, if exploited, could allow an authenticated miscreant (OS Standard User) to trick Process Optimization services into loading arbitrary code and escalate privileges to OS System, potentially resulting in complete compromise of the Model Application Server (CWE-427 Uncontrolled Search Path Element).  

Further privilege escalation vulnerabilities include CVE-2025-64691, which could allow an authenticated miscreant (OS Standard User) to tamper with TCL Macro scripts and escalate privileges to OS System. CVE-2025-64729 could allow an authenticated miscreant (OS Standard User) to tamper with Process Optimization project files, embed code, and escalate their privileges to the identity of a victim user who subsequently interacts with the project files. Similarly, CVE-2025-65117 could allow an authenticated miscreant (Process Optimization Designer User) to embed OLE objects into graphics and escalate their privileges to the identity of a victim user who subsequently interacts with the graphical elements. The Process Optimization application suite also leverages connection channels/protocols that by-default are not encrypted (CVE-2025-64769), which could become subject to hijacking or data leakage in certain man-in-the-Middle or passive inspection scenarios (CWE-319 Cleartext Transmission of Sensitive Information).  

To mitigate these risks, AVEVA recommends users update to AVEVA Process Optimization v2025. Alternatively, users can apply Host and/or Network firewall rules restricting the taoimr service to accept traffic only from trusted source(s); by default, AVEVA Process Optimization listens on port 8888/8889(TLS). Additionally, apply ACLs to the installation and data folders, limiting write-access to trusted users only. Users should also maintain a trusted chain-of-custody on Process Optimization project files during creation, modification, distribution, backups, and use. For more information, users can refer to Aveva's security bulletin AVEVA-2026-001. These vulnerabilities were reported to AVEVA by Christopher Wu of Veracode.

To read the complete article see: [full article](https://www.cisa.gov/news-events/ics-advisories/icsa-26-015-01)  
