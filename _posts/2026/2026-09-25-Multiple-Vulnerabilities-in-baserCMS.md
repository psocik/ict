---
title: Multiple Vulnerabilities in baserCMS
date: 2026-09-25
categories: [SECURITY]
tags: [BASERCMS,VULNERABILITIES,SECURITY,CVE]
---

## Multiple Vulnerabilities in baserCMS 🚨

The baserCMS provided by the baserCMS User Community contains multiple vulnerabilities that could pose significant risks to users. Specifically, baserCMS versions prior to **5.4.1** (5.4 series) and versions prior to **5.3.1** (including all versions prior to 5.3 series) are affected by the following CVEs:
- **CVE-2026-93460**
- **CVE-2026-93462**
- **CVE-2026-93463**
- **CVE-2026-93464**

Additionally, baserCMS versions prior to **5.2.10** (including all versions prior to 5.2 series) are affected by **CVE-2026-62956**.

### Identified Vulnerabilities

The identified vulnerabilities include:
- **Cross-site scripting (CWE-79)**
- **SQL injection (CWE-89)**
- **Missing authentication for critical function (CWE-306)**

For Cross-site scripting vulnerabilities (**CVE-2026-93460**, **CVE-2026-93463**, **CVE-2026-93464**), an arbitrary script may be executed in the user's web browser, which can lead to severe security breaches. These vulnerabilities have a CVSS score of **5.1** and **5.4**.

For SQL injection (**CVE-2026-62956**), information stored in the product's database may be accessed or altered by an attacker with Web API credentials, with a CVSS score of **5.3** and **6.3**.

A Missing authentication for critical function (**CVE-2026-93462**) allows a remote attacker to obtain sensitive information, carrying a CVSS score of **6.9** and **5.3**.

### Recommended Actions

To mitigate these risks, users are advised to **update the software** to the latest version as per the developer's recommendations. The vulnerabilities were reported by several individuals from Mitsui Bussan Secure Directions, Inc.:
- So Kato reported **CVE-2026-93460** to IPA.
- Yuji Tounai reported **CVE-2026-62956** and **CVE-2026-93462** to IPA.
- Gai Tanaka reported **CVE-2026-93463** to IPA.
- Kuniyoshi Noguchi (KuniNogu) reported **CVE-2026-93464** to IPA.

JPCERT/CC coordinated with the developer under the Information Security Early Warning Partnership for all reported vulnerabilities.

For more details, you can read the complete article here: [Read full article](https://jvn.jp/en/jp/JVN14353754/) 
