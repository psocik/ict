---
title: Vulnerabilities in Mira Hormone Monitor and Android App
date: 2026-08-11
categories: [SECURITY]
tags: [MIRA,VULNERABILITIES,HEALTHCARE,SECURITY,ANDROID]
---

## Vulnerabilities in Mira Hormone Monitor and Android App 🚨

The recent report from CISA highlights critical vulnerabilities in the **Mira Hormone Monitor** and its **Android App**. Successful exploitation of these vulnerabilities could allow an attacker to access unauthorized health profile information, make changes to health information, cause a denial-of-service condition, disclose session token information, and obtain control of user accounts.

### Affected Versions
The following versions are affected:
- **Mira Monitor Firmware**: 1.7.1.47
- **Mira Android App**: 4.5.15.4

### Impacted Sectors
The impacted sectors include the **Critical Infrastructure Sectors**: Healthcare and Public Health, with products deployed worldwide.

### Detailed Vulnerabilities
1. **CVE-2026-66875**: In the Mira hormone monitor device firmware, a remote unauthenticated attacker within BLE range can silently rebind the device to an attacker-controlled account, extract stored hormone measurements in cleartext, and cause a denial-of-service.
2. **CVE-2026-67558**: The Mira Android app lacks proper cryptographic peripheral authentication, allowing attackers to capture live session token information.
3. **CVE-2026-67568**: An attacker can gain read/write access to reproductive health profiles from internet-connected hosts.
4. **CVE-2026-68067**: The login endpoint on the Mira cloud API accepts any format-valid string in the password field, allowing unauthorized access.
5. **CVE-2026-66832**: The user's live session token is transmitted to third-party web properties when the app opens in-app WebView content.

### Recommended Actions
Users are advised to update the Mira app to the latest version: **iOS v3.5.18 / Android v4.5.18**. Firmware updates can be done via the app when the device is connected. No additional action is required.

These vulnerabilities were reported to Quanovate Tech by researchers from Northeastern University SPQR Lab.

For more details, [Read full article](https://www.cisa.gov/news-events/ics-medical-advisories/icsma-26-223-01).