---
title: ShinyHunters claims 1.5 billion Salesforce records stolen in Drift hacks
date: 2025-09-17
categories: [SECURITY]
tags: [SHINYHUNTERS,SALESFORCE,DATA BREACH]
---

The ShinyHunters extortion group claims to have stolen over 1.5 billion Salesforce records from 760 companies using compromised Salesloft Drift OAuth tokens.

ShinyHunters told BleepingComputer that the threat actors used the TruffleHog security tool to scan the source code for secrets, which resulted in the finding of OAuth tokens for the Salesloft Drift and the Drift Email platforms.

Using these stolen Drift OAuth tokens, ShinyHunters told BleepingComputer that the threat actors stole approximately 1.5 billion data records for 760 companies from the "Account", "Contact", "Case", "Opportunity", and "User" Salesforce object tables.

Google Threat Intelligence (Mandiant) reported that the stolen Case data was analyzed for hidden secrets, such as credentials, authentication tokens, and access keys, to enable the attackers to pivot into other environments for further attacks. "GTIG observed UNC6395 targeting sensitive credentials such as Amazon Web Services (AWS) access keys (AKIA), passwords, and Snowflake-related access tokens."  

[Read the complete article here](https://www.bleepingcomputer.com/news/security/shinyhunters-claims-15-billion-salesforce-records-stolen-in-drift-hacks/) 

See also:
- [Scattered Spider resurfaces with ...](https://thehackernews.com/2025/09/scattered-spider-resurfaces-with.html)  
- [Jaguar Land Rover cyberattack deepens ...](https://industrialcyber.co/manufacturing/jaguar-land-rover-cyberattack-deepens-with-prolonged-production-outage-supply-chain-fallout/) 