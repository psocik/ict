---
title: A Hacker Claims 35 GB of Accenture Source Code
date: 2026-07-08
categories: [DATA BREACH]
tags: [HACKER,ACCENTURE,DATA BREACH,CYBERSECURITY]
---

## A Hacker Claims 35 GB of Accenture Source Code

Accenture has confirmed a breach after a hacker claimed to have stolen **35 GB** of source code, keys, and Azure credentials, which are now being offered for sale. A threat actor using the handle **"888"** made this claim on the cybercrime forum **PwnForums** this week. The post stated, **"Today I am selling the Accenture Data Breach, thanks for reading and enjoy!"**

The stolen data allegedly includes:
- Source code
- RSA keys
- SSH keys
- Azure personal access tokens
- Azure Storage access keys
- Configuration files

Accenture acknowledged the breach but provided a brief statement that did not address most specific claims. An Accenture spokesperson stated, **"We are aware of this isolated matter, and we have remediated its source. There is no impact to Accenture operations and service delivery."** However, many questions remain unanswered regarding how the attacker gained access, what exactly was taken, and whether any client data was involved.

The threat actor also shared a screenshot that appears to show the cloning of an Azure DevOps repository named **"121123_AtriasTalentAcademy"**, hosted on a partially redacted accenture.com domain. The real danger lies in the fact that SSH and Azure keys can silently authenticate into client environments, while configuration files map production architectures, and source code reveals how client systems were built. Together, these elements provide attackers with a ready-made blueprint.

Although Accenture claims that operations are unaffected, they have not confirmed whether client environments were exposed.

This same threat actor, **"888,"** previously attempted to sell Accenture employee data in 2024 following a third-party breach. Additionally, in 2021, the **LockBit ransomware gang** targeted Accenture and stole data from its systems.

[Read full article](https://securityaffairs.com/194962/data-breach/a-hacker-claims-35-gb-of-accenture-source-code-the-company-discloses-the-data-breach.html)