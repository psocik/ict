---
title: Flaws in Software Used by Hundreds of Cities and Towns Exposed Sensitive Data
date: 2025-08-20
categories: [VULNS]
tags: [SECURITY,VULNERABILITIES,WORKHORSE SOFTWARE]
---

The affected application is made by Workhorse Software Services, which provides software solutions to 310 municipalities in Wisconsin. The vendor has released patches and mitigations after being notified.

The vulnerabilities, discovered by researcher James Harrold of Sparrow IT Solutions, were disclosed this week by the CERT Coordination Center (CERT/CC) at Carnegie Mellon University. 

One of the flaws, tracked as CVE-2025-9037, is an information exposure issue related to SQL server connection credentials being stored in a plaintext file that is typically in a shared network folder. The second issue, CVE-2025-9040, is related to the availability of a database backup feature accessible from the login screen that allows the creation of an unencrypted database backup file, which can later be restored on any SQL server without a password.

To read the complete article see:

[Flaws in Software Used by Hundreds of Cities and Towns Exposed Sensitive Data](https://www.securityweek.com/flaws-in-software-used-by-hundreds-of-cities-and-towns-exposed-sensitive-data/) 