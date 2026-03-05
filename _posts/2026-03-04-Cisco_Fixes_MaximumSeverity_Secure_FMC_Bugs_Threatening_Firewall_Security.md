---
title: Cisco Fixes Maximum-Severity Secure FMC Bugs Threatening Firewall Security
date: 2026-03-04
categories: [CYBERSECURITY]
tags: [CISCO,FIREWALL,SECURITY,VULNERABILITIES]
---

## Cisco Fixes Maximum-Severity Secure FMC Bugs 🚀

Cisco has addressed two maximum-severity vulnerabilities in its Secure Firewall Management Center (FMC) that could allow attackers to gain root access. The Cisco Secure Firewall Management Center (FMC) is a centralized management platform for Cisco firewalls, enabling administrators to configure, monitor, and control multiple firewalls from a single web or SSH interface.

### Vulnerabilities Overview

1. **CVE-2026-20079** (CVSS score of 10.0): This vulnerability is an authentication bypass issue. It resides in Cisco Secure FMC’s web interface, allowing unauthenticated remote attackers to bypass authentication and send crafted HTTP requests to execute scripts, potentially gaining root access to the underlying operating system. The advisory states, "A vulnerability in the web interface of Cisco Secure Firewall Management Center (FMC) Software could allow an unauthenticated, remote attacker to bypass authentication and execute script files on an affected device to obtain root access to the underlying operating system."

2. **CVE-2026-20131** (CVSS score of 10.0): This vulnerability is a remote code execution issue. It allows unauthenticated remote attackers to exploit insecure Java deserialization and execute arbitrary code as root by sending a crafted serialized object. The advisory mentions, "A vulnerability in the web-based management interface of Cisco Secure Firewall Management Center (FMC) Software could allow an unauthenticated, remote attacker to execute arbitrary Java code as root on an affected device."

### Company Statement

Cisco's PSIRT has stated that it is not aware of any public disclosure or active exploitation of both vulnerabilities. The company also mentioned that there are no workarounds that address these flaws.

For more details, you can read the complete article here: [Read full article](https://securityaffairs.com/188921/security/cisco-fixes-maximum-severity-secure-fmc-bugs-threatening-firewall-security.html)