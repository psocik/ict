---
title: 30 Million Sensitive Records Leaked Numerous PepsiCo Locations Exposed
date: 2026-09-23
categories: [DATA BREACH]
tags: [DATA BREACH,PEPSICO,SENSITIVE INFORMATION,CYBERSECURITY]
---

## 30 Million Sensitive Records Leaked: Numerous PepsiCo Locations Exposed

E-documents manager **EDX Solutions** has leaked hundreds of gigabytes of data, exposing tens of millions of records. Our researchers, who discovered the leak, found employee accounts, plaintext credentials, invoices, and other sensitive information. The sensitive data included customer information belonging to **PepsiCo** and other organizations in countries such as **Mexico**, **Pakistan**, the **Dominican Republic**, and the **US**. The Cybernews research team discovered a publicly accessible MongoDB instance belonging to EDX Solutions, a company that manages e-documents and financial information for businesses in Latin America and other regions. The exposed database contained **292GB** of data. Based on our preliminary analysis, the researchers estimate that at least **30 million sensitive records** were exposed.

EDX Solutions provides services to numerous large companies, including PepsiCo, according to their website and the exposed database. The most impacted organization by the leak appears to be PepsiCo's Latin America operations. The exposed data included:
- Invoices, including details like transaction type, vendor, client, recipient, subtotal, and tax amounts.
- Tax documents and related information.
- Employee accounts with hashed and some plaintext credentials.
- Full names of employees and clients.
- API tokens for various services.
- Unencrypted payment details.
- Supplier details.
- Purchase order information.

"This data could be very valuable for threat actors. By gaining access to this information, attackers could conduct highly effective phishing attacks on employees, execute account takeovers, or attempt identity theft," said Cybernews researcher **Aras Nazarovas**. "Since the leak contains detailed financial and transactional data, it could also be used for **Business Email Compromise (BEC)** attacks, where attackers impersonate an executive to trick employees into transferring money or sensitive information," Nazarovas added. According to the researcher, the plain-text credentials and API tokens could allow attackers to pivot deeper into organizations or automate data exfiltration processes. The exposed supplier details could also be leveraged for supply chain attacks. Invoices, tax documents, and purchase order information could be used for financial fraud and tax evasion schemes.

The exposed data includes information from various organizations in at least eight countries, including **Mexico**, **Brazil**, the **US**, the **Dominican Republic**, and **Pakistan**. Our researchers immediately reported their findings to EDX Solutions to ensure the database was secured. The database has since been taken offline, but it is unclear if any unauthorized third parties accessed the data before it was secured.

[Read full article](https://cybernews.com/security/edx-solutions-data-leak-pepsico-exposed/) 
