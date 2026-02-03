---
title: Multiple vulnerabilities in Cybozu Garoon
date: 2026-02-02
categories: [VULNERABILITY REPORT]
tags: [CYBOZU,VULNERABILITIES,CVE]
---

Multiple vulnerabilities have been identified in Cybozu Garoon, detailed in JVN#35265756 and published on 2026/02/02. Cybozu Garoon provided by Cybozu, Inc. contains these multiple vulnerabilities. Products affected include Cybozu Garoon 5.0.0 to 6.0.3 and Cybozu Garoon 5.15.0 to 6.0.3.

One vulnerability is a cross-site scripting vulnerability in E-mail (CWE-79), identified as CVE-2026-20711 (CyVDB-3687). This vulnerability has a CVSS:4.0 base score of 6.9 and a CVSS:3.0 base score of 6.5. 

Additionally, a cross-site scripting vulnerability in Message (CWE-79), identified as CVE-2026-22881 (CyVDB-3689), also affects the software. This vulnerability carries a CVSS:4.0 base score of 6.8 and a CVSS:3.0 base score of 5.7. 

Furthermore, an improper input verification vulnerability in Portal setting (CWE-231), labeled CVE-2026-22888 (CyVDB-3995), is present. Its CVSS:4.0 base score is 6.9 and CVSS:3.0 base score is 4.9. 

An attacker could exploit a cross-site scripting vulnerability to reset arbitrary users’ passwords (CVE-2026-20711, CVE-2026-22881). Data related to portal settings may be altered, potentially blocking access to the product (CVE-2026-22888). 

As a solution, update the software to the latest version according to the information provided by the developer. Masato Kinugawa reported CVE-2026-20711 to Cybozu, Inc. and Cybozu, Inc. reported it to JPCERT/CC to notify users of its solution through JVN. CVE-2026-22881 and CVE-2026-22888 were reported by Cybozu, Inc. to JPCERT/CC to notify users of the solutions through JVN.

To read the complete article see:
[Complete Article](https://jvn.jp/en/jp/JVN35265756/) 
