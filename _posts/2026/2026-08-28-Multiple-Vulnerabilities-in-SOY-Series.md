---
title: Multiple Vulnerabilities in SOY Series
date: 2026-08-28
categories: [SECURITY]
tags: [VULNERABILITIES,SOY,SECURITY,SOFTWARE]
---

## Multiple Vulnerabilities in SOY Series 🚨

Multiple vulnerabilities have been identified in the SOY series provided by Tsuyoshi Saito. These vulnerabilities affect:

- **SOY Calendar** ver 2.4.0 and earlier (CVE-2026-73827, CVE-2026-77838)
- **SOY CMS** ver 3.24.0 and earlier (CVE-2026-78032)
- **SOY Gallery** ver 2.0.0 and earlier (CVE-2026-78238)

It is important to note that the SOY series provided by Brassica, Inc. is not affected by these vulnerabilities.

### Types of Vulnerabilities
The SOY series contains multiple vulnerabilities, including:
- **Cross-site Scripting (CWE-79)**
- **Deserialization of Untrusted Data (CWE-502)**

The Cross-site Scripting vulnerabilities (CVE-2026-73827, CVE-2026-77838, CVE-2026-78238) have a CVSS score of 4.0 and a Base Score of 4.8. The Deserialization of Untrusted Data vulnerability (CVE-2026-78032) carries a CVSS score of 9.3 and a Base Score of 9.8.

### Impact
The Cross-site Scripting vulnerabilities could allow an arbitrary script to be executed on the web browser of the user logging in to the product. For the Deserialization of Untrusted Data vulnerability, arbitrary code may be executed by an attacker with web server privileges.

### Recommendations
To address these vulnerabilities, users are advised to update the software to the latest version according to the information provided by the developer.

These vulnerabilities were reported to IPA by Shogo Kumamaru of LAC Co., Ltd. JPCERT/CC coordinated with the developer, Tsuyoshi Saito, under the Information Security Early Warning Partnership. Tsuyoshi Saito has since released security updates for SOY CMS and related plugins.

[Read full article](https://jvn.jp/en/jp/JVN04485476/)\n