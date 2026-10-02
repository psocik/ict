---
title: Armatura LLC Armatura One Vulnerabilities
date: 2026-10-01
categories: [SECURITY]
tags: [ARMATURA,VULNERABILITIES,SECURITY,CISA]
---

## Armatura LLC Armatura One Vulnerabilities

**Published Date:** October 1, 2026  
**Source:** CISA  

The recent vulnerabilities discovered in Armatura LLC's Armatura One could lead to serious security risks. 🚨 Successful exploitation of these vulnerabilities may allow an attacker to gain unauthorized access to the database, execute arbitrary code on the host with the highest level of privilege, or even control the physical access-control system. 

### Affected Versions
The following versions are impacted:  
- Armatura One < 4.7.2  
- Armatura One (USA) < 4.6.1  

### Key Vulnerabilities
1. **CVE-2023-46604**: This critical vulnerability arises because Armatura One embeds Apache ActiveMQ, exposing its OpenWire protocol listener on the network by default. This flaw allows an unauthenticated network attacker to trigger deserialization of an arbitrary object graph, leading to arbitrary code execution with the highest privileges.  
2. **Credential Handling Issues**:  
   - **CVE-2026-94591**: Database and message-broker credentials are stored in an install configuration file, encrypted with AES-128-CBC. However, the encryption key is fixed and can be easily recovered.  
   - **CVE-2026-94592**: A fixed, vendor-defined password is assigned to the database superuser account at creation time, which can be exploited by individuals with server access.  
   - **CVE-2026-94593**: The backup and restore routine logs the full database connection command, including the superuser password, in plain text.  
   - **CVE-2026-94594**: Client connection credentials are logged in plain text during normal operation.  

### Recommendations
Armatura LLC has released Armatura One V4.7.2 to resolve these issues. Users are urged to upgrade from V4.7.1 or earlier to V4.7.2. For the USA release line, upgrade from V4.3.1_USA to V4.6.1_USA.  

CISA recommends minimizing network exposure for all control system devices and ensuring they are not accessible from the internet. It is advisable to locate control system networks behind firewalls and isolate them from business networks.  

For more detailed information, visit the full article: [Read full article](https://www.cisa.gov/news-events/ics-advisories/icsa-26-274-01)  

Stay safe and secure! 🔒