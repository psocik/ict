---
title: Supply-chain attack hits Zscaler via Salesloft Drift, leaking customer info
date: 2025-09-01
categories: [SECURITY]
tags: [SUPPLY-CHAIN ATTACK,ZSCALER,SALESLOFT,DATA BREACH]
---

Beginning as early as Aug. 8, 2025 through at least Aug. 18, 2025, the actor targeted Salesforce customer instances through compromised OAuth tokens associated with the Salesloft Drift third-party application. The actor systematically exported large volumes of data from numerous corporate Salesforce instances.

From August 8 to August 18, 2025, a threat actor used OAuth credentials to exfiltrate data from our customers’ Salesforce instances. All impacted customers have been notified. Initial findings have shown that the actor’s primary objective was to steal credentials, specifically focusing on sensitive information like AWS access keys, passwords, and Snowflake-related access tokens. This incident did not impact customers who do not use our Drift-Salesforce integration.

On August 28, 2025, our investigation confirmed that the actor also compromised OAuth tokens for the "Drift Email" integration. On August 9, 2025, a threat actor used these tokens to access email from a very small number of Google Workspace accounts. The only accounts that were potentially accessed were those that had been specifically configured to integrate with Salesloft; the actor would not have been able to access any other accounts on a customer’s Workspace domain.

For the complete article, see: [full article](https://securityaffairs.com/181801/data-breach/supply-chain-attack-hits-zscaler-via-salesloft-drift-leaking-customer-info.html).