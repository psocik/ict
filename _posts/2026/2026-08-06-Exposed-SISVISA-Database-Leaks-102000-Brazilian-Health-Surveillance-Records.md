---
title: Exposed SISVISA Database Leaks 102,000 Brazilian Health Surveillance Records
date: 2026-08-06
categories: [DATA BREACH]
tags: [DATA BREACH,HEALTH RECORDS,BRAZIL,SECURITY]
---

## Exposed SISVISA Database Leaks 102,000 Brazilian Health Surveillance Records 🚨

An exposed SISVISA database has leaked **102,215 Brazilian health records**, revealing sensitive information such as IDs, tax data, and regulatory documents without any authentication. Researcher **Jeremiah Fowler** discovered a publicly accessible database belonging to SISVISA, Brazil's Health Surveillance Information System, and promptly alerted **ExpressVPN**, which later shared the findings with **Hackread**.

The exposed database contained approximately **79 GB of data** tied to a platform used by regulators to track health rules, issue licenses, and manage inspections for hospitals, restaurants, and pharmacies. Fowler noted that anyone who knew the URL could easily browse folders labeled "backups", "imports", "documents", and "uploads" without needing to log in. Inside, sensitive data included full names, home addresses, phone numbers, CPF and CNPJ tax IDs, scans of driver's licenses, federal doctor ID cards, photos of faces, fingerprints, inspection reports, and complaint records. This kind of data can enable attackers to impersonate individuals, run phishing campaigns, open lines of credit, or even introduce malware into documents.

Fowler sent urgent notices to several agencies regarding the exposed data, and public access was revoked shortly thereafter. However, no responses were received, leaving uncertainty about how long the data was exposed or if it had been accessed by unauthorized individuals. This lack of communication raises significant concerns about accountability and responsibility for such critical data.

From a security perspective, this incident highlights the dangers of having a critical system without proper authentication or encryption. The implications for identity fraud and long-term abuse of personal data are severe. If you suspect that you or your organization might be affected by this data leak, it is crucial to monitor financial accounts closely and treat unexpected communications regarding tax IDs or licenses as potentially malicious. Additionally, enabling multi-factor authentication wherever possible is highly recommended.

For more details, [Read full article](https://securityaffairs.com/196766/data-breach/exposed-sisvisa-database-leaks-102000-brazilian-health-surveillance-records.html)