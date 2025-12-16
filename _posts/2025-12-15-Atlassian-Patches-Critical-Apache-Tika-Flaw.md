---
title: Atlassian Patches Critical Apache Tika Flaw
date: 2025-12-15
categories: [SECURITY]
tags: [ATLASSIAN,APACHE TIKA,CVE-2025-66516,VULNERABILITIES,SECURITY ADVISORY]
---

Atlassian has recently addressed a series of critical vulnerabilities affecting its suite of products, with a particular focus on a severe flaw in Apache Tika. The vulnerability, identified as CVE-2025-66516, has been assigned a maximum CVSS score of 10/10, highlighting its critical nature. This XML External Entity (XXE) injection bug impacts the tika-core, tika-pdf-module, and tika-parsers modules of the universal parser. Disclosed in early December, the flaw can be exploited through crafted XFA files embedded within PDF documents, potentially leading to severe consequences such as information leaks, denial-of-service (DoS) attacks, server-side request forgery (SSRF), or even remote code execution (RCE).

The affected Atlassian products include Bamboo, Confluence, Crowd, Fisheye/Crucible, Jira, and Jira Service Management, all of which have received necessary patches. In addition to the Apache Tika flaw, Atlassian has also resolved other critical vulnerabilities this month. Notably, CVE-2022-37601, a prototype pollution vulnerability in webpack loader-utils used by Confluence, and CVE-2021-39227, another prototype pollution bug affecting the ZRender graphic library in Jira and Jira Service Management, both carry a CVSS score of 9.8. These vulnerabilities, if left unpatched, could allow attackers to manipulate object properties, leading to potential application compromise.

Beyond these critical issues, Atlassian's latest security updates address over two dozen high-severity vulnerabilities, including DoS, XXE, SSRF, file inclusion, improper authorization, information disclosure, improper input validation, and RCE flaws. The updates are applicable to a range of Atlassian products, including Bamboo, Bitbucket, Confluence, Crowd, Fisheye/Crucible, Jira, and Jira Service Management, covering both data center and server products. Given that these vulnerabilities stem from third-party dependencies, they pose a risk to all Atlassian products that incorporate these components. Consequently, users are strongly advised to implement the patches promptly to mitigate potential security risks. Further details on these vulnerabilities and their corresponding fixes are available in Atlassian’s December 2025 security advisory.

To read the complete article see:
[SecurityWeek](https://www.securityweek.com/atlassian-patches-critical-apache-tika-flaw/) 
