---
title: Northflank Security Breach Leads to Abuse of Customers' AI API Keys
date: 2026-10-31
categories: [SECURITY]
tags: [NORTHFLANK,SECURITY,API,BREACH,CUSTOMERS]
---

## Northflank Security Breach 🚨

Cloud application hosting platform **Northflank** is warning customers to rotate all credentials and secrets stored on its platform after a security breach led to unauthorized use of customers' AI API keys. The company disclosed a security incident on **October 30**, urging customers to immediately rotate their environment variables and API keys after receiving a threat alert from cloud security company **Wiz**.

### Key Details:
- Northflank advised all customers to assume their environment variables had been decrypted and that the secrets stored within them were stolen. 
- "Assume all environment variables have been decrypted. Disable/rotate all keys," Northflank warned in an update on **October 30**.

Applications commonly use environment variables to store sensitive information, including database passwords, cloud service credentials, authentication tokens, and API keys. If exposed, these credentials can lead to data theft or unauthorized charges through API keys. Northflank later confirmed that multiple customers had reported unauthorized use of AI API keys stored on the platform.

### Incident Timeline:
- Wiz warned Northflank about the breach at **11:43 UTC** on **October 30**.
- Northflank quickly responded with a network policy patch, followed by additional patches at **12:50 UTC** and **13:05 UTC**.
- The company also enabled audit logs for all customers, including those using free accounts, to help them investigate any suspicious activity.

The breach comes amid a series of attacks targeting AI development platforms, which security researchers believe are valuable targets due to the storage of API keys that can access expensive AI services. In a report titled **"Black October for AI Developer Platforms,"** Wiz identified at least nine security incidents affecting AI development platforms during the month, including Northflank, Railway, OpenCode, Warp, and Lightning AI.

### Security Implications:
Wiz says attackers involved in some of these incidents have specifically targeted environment variables containing AI service credentials, which can be exploited through a practice known as **LLMJacking**. This involves using stolen credentials to access AI models using another organization's API keys, generating massive API charges or allowing the stolen access to be resold. In two cases investigated by Wiz, compromised enterprise credentials were used to make approximately **2.5 million Amazon Bedrock API calls**, generating around **$100,000** in AI usage.

Northflank also referenced Wiz's research in its incident updates, noting that customer reports of unauthorized AI key usage may be tied to the attacks seen by the researchers. Northflank continues to advise customers to rotate secrets stored in workloads, secret groups, and global secrets, and to disable public access to add-ons where enabled.

For more information, please read the full article: [Read full article](https://www.bleepingcomputer.com/news/security/northflank-security-breach-leads-to-abuse-of-customers-ai-api-keys/) 
