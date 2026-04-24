---
title: Critical Ubiquiti UniFi Security Flaw Allows Potential Account Hijacking
date: 2026-03-19
categories: [SECURITY]
tags: [UBIQUITI,UNIFI,SECURITY,VULNERABILITY]
---

## Critical Ubiquiti UniFi Security Flaw 🚨

Ubiquiti has addressed two vulnerabilities in its UniFi Network app, including a **critical flaw** that could allow attackers to take over user accounts. This software is widely used to manage UniFi networking devices such as access points, switches, and gateways.

The **Ubiquiti UniFi Network app** is management software developed by Ubiquiti to control and monitor its networking devices. It enables users to configure, manage, and optimize hardware from a single dashboard. IT admins utilize it to set up networks, track performance, manage users, apply security settings, and troubleshoot issues, either locally or via the cloud.

### Key Vulnerabilities Addressed:
- **CVE-2026-22557**: A maximum severity issue (CVSS score of 10.0) affecting UniFi Network application version 10.1.85 and earlier. An attacker on the network could exploit a path traversal flaw to access system files and potentially take over user accounts.
- **CVE-2026-22558**: A second issue with a CVSS score of 7.7, which allows attackers with low privileges to escalate their access.

According to the advisory, "A malicious actor with access to the network could exploit a Path Traversal vulnerability found in the UniFi Network Application to access files on the underlying system that could be manipulated to access an underlying account." Versions 10.1.89 or later have addressed these vulnerabilities.

For more details, see the complete article: [Read full article](https://securityaffairs.com/189689/security/critical-ubiquiti-unifi-unifi-security-flaw-allows-potential-account-hijacking.html)