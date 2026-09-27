---
title: Eufy Omni C20 and Omni X10 Pro Vulnerabilities
date: 2026-09-24
categories: [CYBERSECURITY]
tags: [EUFY,VULNERABILITIES,CYBERSECURITY,CISA]
---

## Eufy Omni C20 and Omni X10 Pro Vulnerabilities 🚨

**Date Published:** September 24, 2026  
**Source:** CISA  

Successful exploitation of these vulnerabilities could allow an attacker to run system-level commands or execute arbitrary code. The following versions of Eufy Omni C20 and Omni X10 Pro are affected:  
- Omni C20 < 1.6.4 (CVE-2026-93289, CVE-2026-93290, CVE-2026-93291)  
- Omni X10 Pro < 1.6.4 (CVE-2026-93289)  

These vulnerabilities were reported to CISA by Jared of Somerset Recon. CISA initially released this information on 2026-09-24.

### Details of the Vulnerabilities  
Specifically, CVE-2026-93289 affects both Eufy Omni C20 and Omni X10 Pro, where the affected products are vulnerable to command injection attacks that could allow an unauthenticated attacker to execute system commands during the pairing process. The Omni C20 also faces two additional vulnerabilities:  
- **CVE-2026-93290** indicates that Omni C20 uses hard-coded credentials that could allow an attacker to monitor log files to obtain credentials to access sensitive information like mapping data.  
- **CVE-2026-93291** highlights that Omni C20 lacks proper certificate validation, which could allow an attacker to perform a man-in-the-middle attack, enabling them to execute arbitrary code.

### Recommendations  
Eufy recommends users upgrade to version 1.6.4 or later for all affected devices. CISA advises users to take defensive measures to minimize the risk of exploitation of these vulnerabilities. Organizations should minimize network exposure for all control system devices and/or systems, ensuring they are not accessible from the internet. Control system networks and remote devices should be located behind firewalls and isolated from business networks. When remote access is required, CISA advises using more secure methods, such as Virtual Private Networks (VPNs).  

CISA reminds organizations to perform proper impact analysis and risk assessment prior to deploying defensive measures. They encourage organizations to implement recommended cybersecurity strategies for proactive defense of ICS assets. Organizations observing suspected malicious activity should follow established internal procedures and report findings to CISA for tracking and correlation against other incidents. No known public exploitation specifically targeting these vulnerabilities has been reported to CISA at this time.

For more details, [Read full article](https://www.cisa.gov/news-events/ics-advisories/icsa-26-267-02)  
