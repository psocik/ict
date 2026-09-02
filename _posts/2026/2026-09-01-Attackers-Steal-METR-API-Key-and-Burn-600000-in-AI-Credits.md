---
title: Attackers Steal METR API Key and Burn $600,000 in AI Credits
date: 2026-09-01
categories: [CYBERSECURITY]
tags: [API,SECURITY,ATTACK,CREDITS,METR]
---

## Attackers Steal METR API Key and Burn $600,000 in AI Credits 🚨

Attackers have stolen an API key from the AI safety research organization METR and used it for three weeks to consume model credits worth about **$600,000**. METR disclosed the incident in a security update published on **August 31**, highlighting a separate attack in May where threat actors probed its public infrastructure. Fortunately, there was no evidence that sensitive information was accessed in either incident.

The credits were supplied free of charge by an unnamed model developer, meaning the $600,000 represents their commercial value rather than a direct financial loss. METR clarified that the disclosure concerned external attackers rather than AI agents acting within its evaluations.

### Incident Overview

The incident began in **March** when a METR researcher ran agents on a personal Amazon EC2 instance that was made publicly accessible behind Google authentication. The vibe-coded app held an API key for METR's public models account. A fail-open flaw silently disabled authentication, leaving the system exposed for several days. METR suspects the attacker found the instance by mining certificate transparency lists for recently registered sites with high-signal terms related to language models and agents.

The attacker prompted an agent to reveal the model provider API key and added an SSH key for persistence, then used the stolen credentials to consume large volumes of model credits over three weeks. METR noted that the illicit usage was hard to distinguish from legitimate evaluation activity, as its researchers routinely generated high volumes of model traffic, and there was no way to cap spending on free-credit keys. The organization revoked the researcher's access, rotated credentials, wiped the laptop, and alerted the model developer. They later added spend alerts to keys where possible.

### Additional Attacks

Moreover, METR reported being tipped off in early May about attackers who appeared financially motivated and may have been seeking frontier model access. The attackers heavily utilized agents to automate vulnerability discovery, including credential stuffing, OAuth token grant attempts, scanning of new services, and attempts to phish staff. METR also inadvertently exposed a read-only SQL query mechanism through its public transcript viewer. A bug could have been exploited to reach unpublished evaluation data, and the database had accidentally been loaded with sensitive model data it was not meant to hold. An independent researcher disclosed the flaw, prompting METR to take the interface offline and pay a bounty. The attackers probed the endpoint without appearing to discover or exploit the bug.

METR now runs public-facing applications in an environment architecturally separated from its internal infrastructure.

[Read full article](https://www.infosecurity-magazine.com/news/attackers-steal-metr-api-key/)  
