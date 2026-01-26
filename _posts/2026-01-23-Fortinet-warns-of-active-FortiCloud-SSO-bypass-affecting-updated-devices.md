---
title: Fortinet warns of active FortiCloud SSO bypass affecting updated devices
date: 2026-01-23
categories: [SECURITY]
tags: [FORTINET,SSO,CYBERSECURITY,SECURITY AFFAIRS]
---

Fortinet confirmed attacks are bypassing FortiCloud SSO authentication, affecting even fully patched devices, similar to recent SSO flaws. Threat actors automate firewall changes, add users, enable VPNs, and steal configs, in campaigns resembling December 2025 exploits of critical FortiCloud SSO flaws. 

This week, Fortinet confirmed that attacks succeeded even against devices patched for CVE-2025-59718 and CVE-2025-59719. The company identified a new attack path after observing login exploits on fully updated devices. A fix is in progress, an advisory is pending, and all SAML SSO implementations may be affected. 

“Recently, a small number of customers reported unexpected login activity occurring on their devices, which appeared very similar to the previous issue. However, in the last 24 hours, we have identified a number of cases where the exploit was to a device that had been fully upgraded to the latest release at the time of the attack, which suggested a new attack path.” reads the advisory published by the company.

Starting on January 15, 2026, Arctic Wolf began observing a new cluster of automated malicious activity involving unauthorized firewall configuration changes on FortiGate devices. Recent intrusions show malicious SSO logins from a small set of hosting providers, often targeting the admin@fortinet.com account. 

After successful SSO access, attackers quickly exported firewall configurations via the GUI and created secondary admin accounts for persistence. These actions occurred within seconds, suggesting highly automated activity. 

In December 2025, Fortinet disclosed two critical SSO authentication bypass flaws, tracked as CVE-2025-59718 and CVE-2025-59719, which are improper verification of cryptographic signature issues. Threat actors started exploiting the two critical flaws in Fortinet products days after patch release. Arctic Wolf warned that attackers began exploiting critical Fortinet authentication bypass flaws on December 12, just three days after patches were issued.

Fortinet product security has identified the issue, and the company is working on a fix to remediate this occurrence. An advisory will be issued as the fix scope and timeline is available. It is important to note that while, at this time, only exploitation of FortiCloud SSO has been observed, this issue is applicable to all SAML SSO implementations. Fortinet is developing a fix. Customers are urged to restrict admin access, limit it to local IPs, and temporarily disable FortiCloud SSO as a workaround.

To read the complete article see: [Security Affairs](https://securityaffairs.com/187250/security/fortinet-warns-of-active-forticloud-sso-bypass-affecting-updated-devices.html).