---
title: Siemens COMOS
date: 2025-11-13
categories: [VULNS]
tags: [CISA,SIEMENS,VULNERABILITIES]
---

Siemens COMOS, a software used in critical manufacturing, is affected by two vulnerabilities that could allow attackers to execute arbitrary code or infiltrate data. Siemens has released updates to address these issues, and CISA urges users to apply these mitigations promptly. 

The vulnerabilities, reported by Siemens ProductCERT, affect Siemens COMOS with COMOS Web deployed (versions prior to 10.4.5) and Siemens COMOS using the COMOS Snapshots component (versions prior to 10.4.5).

### Vulnerabilities Overview

1. **CVE-2023-45133**: This vulnerability stems from an incomplete list of disallowed inputs (CWE-184) in the Babel JavaScript compiler. Using Babel to compile maliciously crafted code could lead to arbitrary code execution during compilation, especially with certain plugins. This vulnerability has a CVSS v3.1 base score of **9.3**, indicating critical severity.

2. **CVE-2024-0056**: This involves the cleartext transmission of sensitive information (CWE-319) related to Microsoft.Data.SqlClient and System.Data.SqlClient SQL Data Provider security feature bypass. This vulnerability has a CVSS v3.1 base score of **8.7**.

Siemens recommends updating to COMOS V10.4.5 or later to mitigate these vulnerabilities. They also advise protecting network access to devices with appropriate mechanisms and configuring the environment according to Siemens' operational guidelines for industrial security. CISA further recommends minimizing network exposure for control system devices and securing remote access via updated VPNs.

To read the complete article see: [CISA Advisory](https://www.cisa.gov/news-events/ics-advisories/icsa-25-317-15) 
