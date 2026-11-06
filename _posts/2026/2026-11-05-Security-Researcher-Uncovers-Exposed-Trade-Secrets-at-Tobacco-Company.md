---
title: Security Researcher Uncovers Exposed Trade Secrets at Tobacco Company
date: 2026-11-05
categories: [SECURITY]
tags: [SECURITY,TRADE-SECRETS,TOBACCO,VULNERABILITIES,PENETRATION-TESTING]
---

## Security Researcher Uncovers Exposed Trade Secrets at Tobacco Company

A professional penetration tester discovered significant security vulnerabilities within a tobacco company, exposing sensitive trade secrets and internal product recipes to unauthorized access. 🚨

During a network assessment, penetration tester Dahvid Schloss utilized tools like Metasploit to probe the company's infrastructure. He noted that the organization's antivirus software failed to trigger alerts despite his aggressive scanning. Schloss eventually identified an open network file share accessible to all employees without authentication. By utilizing Nmap, he confirmed that ports 139 and 445 were open, facilitating access to sensitive human resources and IT records. Within a folder labeled **confidential**, he located files containing detailed chemical compositions and manufacturing specifications for tobacco products.

Although Schloss initially downloaded the data to demonstrate the risk, his manager instructed him to delete the files to avoid retaining sensitive information. When Schloss reported the findings, the company's security team denied the existence of the files and the validity of the security gap. The files were later removed from the network, suggesting the company attempted to conceal the breach rather than address the underlying security failures. This case highlights the risks of poor internal access controls and the potential for corporate denial when faced with critical security vulnerabilities. 🔍

[Read full article](https://www.scworld.com/brief/security-researcher-uncovers-exposed-trade-secrets-at-tobacco-company)