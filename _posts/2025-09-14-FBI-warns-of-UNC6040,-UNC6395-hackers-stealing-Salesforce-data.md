---
title: FBI warns of UNC6040, UNC6395 hackers stealing Salesforce data
date: 2025-09-14
categories: [SECURITY]
tags: [FBI,SALESFORCE,CYBERSECURITY]
---

The FBI has issued a FLASH alert warning that two threat clusters, tracked as UNC6040 and UNC6395, are compromising organizations’ Salesforce environments to steal data and extort victims.

UNC6040 was first disclosed by Google Threat Intelligence (Mandiant) in June, who warned that since late 2024, threat actors were using social engineering and vishing attacks to trick employees into connecting malicious Salesforce Data Loader OAuth apps to their company's Salesforce accounts.

This activity is tracked as UNC6395 and is believed to have occurred between August 8th and 18th, with the threat actors using the tokens to target the company's support case information that was stored in Salesforce. The exfiltrated data was then analyzed to extract secrets, credentials, and authentication tokens shared in support cases, including AWS keys, passwords, and Snowflake tokens. These credentials could then be used to pivot to other cloud environments for additional data theft.

Like the previous attacks, these new Salesloft Drift data theft attacks impacted numerous companies, including Cloudflare, Zscaler, Tenable, CyberArk, Elastic, BeyondTrust, Proofpoint, JFrog, Nutanix, Qualys, Rubrik, Cato Networks, Palo Alto Networks, and many more.

To read the complete article, see: [FBI warns of UNC6040, UNC6395 hackers stealing Salesforce data](https://www.bleepingcomputer.com/news/security/fbi-warns-of-unc6040-unc6395-hackers-stealing-salesforce-data/)