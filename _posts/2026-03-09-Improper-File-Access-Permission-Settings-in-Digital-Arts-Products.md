---
title: Improper File Access Permission Settings in Digital Arts Products
date: 2026-03-09
categories: [SECURITY]
tags: [DIGITAL ARTS,VULNERABILITY,SECURITY,CVE]
---

## Improper File Access Permission Settings in Digital Arts Products 🚨

Multiple products provided by Digital Arts Inc. are configured with improper file access permission settings. This vulnerability, categorized as **Incorrect Default Permissions (CWE-276)**, is identified as **CVE-2026-28267**. It carries a **CVSS:4.0 Base Score of 6.8** and a **CVSS:3.0 Base Score of 5.5**.

### Impact ⚠️
The impact of this vulnerability is significant: files may be created or overwritten in the system directory or backup directory by a non-administrative user. A wide range of Digital Arts Inc. products are affected, including:
- i-フィルター 10 (Windows version only) versions prior to Ver.10.02.00
- i-フィルター 6.0 versions prior to Ver.6.00.57
- i-フィルター for ネットカフェ versions prior to Ver.6.10.57
- i-フィルター for マルチデバイス (Windows version only) versions prior to Ver.6.00.57
- i-フィルター for ZAQ (Windows version only) versions prior to Ver.6.00.57
- i-フィルター for プロバイダー versions prior to Ver.2.00.30
- i-FILTER ブラウザー＆クラウド MultiAgent for Windows versions prior to Ver.4.93R13
- DigitalArts@Cloud Agent (for Windows) versions prior to Ver.1.70R01

It is important to note that i-フィルター is only available in Japan and is different from Digital Arts Inc.’s i-FILTER, which has the same pronunciation. This vulnerability does not affect Digital Arts’ i-FILTER.

### Other Affected Products 🔍
Furthermore, products from other vendors that incorporate Digital Arts technology are also impacted:
- Optimal Biz Web Filtering Powered by i-FILTER (Windows version) versions prior to 4.93R13, provided by OPTiM Corporation
- MobiConnect i-FILTER Browser Option MultiAgent for Windows versions prior to Ver.4.93R13, from Inventit Inc.
- i-FILTER Browser & Cloud MultiAgent for Windows versions prior to Ver.4.93R13, from Fujitsu Limited.

### Mitigation 🛡️
To mitigate this vulnerability, users should update the software to the latest version according to the information provided by the developer. This vulnerability was reported by Kazuma Matsumoto of GMO Cybersecurity by IERAE, Inc. to IPA. JPCERT/CC coordinated with the developer under the Information Security Early Warning Partnership.

For more details, [Read full article](https://jvn.jp/en/jp/JVN17307628/)