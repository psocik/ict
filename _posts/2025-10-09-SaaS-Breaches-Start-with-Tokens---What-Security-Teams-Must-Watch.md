---
title: SaaS Breaches Start with Tokens - What Security Teams Must Watch
date: 2025-10-09
categories: [POLICY]
tags: [SAAS,SECURITY,BREACH]
---

Most companies in 2025 rely on a whole range of software-as-a-service (SaaS) applications to run their operations. However, the security of these applications depends on small pieces of data called tokens. Tokens, like OAuth access tokens, API keys, and session tokens, work like keys to these applications. If a cybercriminal gets hold of one, they can access relevant systems without much trouble.

Recent security breaches have shown that just one stolen token can bypass multi-factor authentication (MFA) and other security measures. Instead of exploiting vulnerabilities directly, attackers are leveraging token theft. It's a security concern that ties into the broader issue of SaaS sprawl and the difficulty of monitoring countless third-party integrations.

For example, in January 2023, information-stealing malware on an engineer's laptop allowed threat actors to hijack session tokens for CircleCI's systems. Those tokens gave the attackers the same access as the user, even with MFA in place, enabling them to steal customer secrets from the CI platform.

Single sign-on (SSO) and multi-factor authentication protect user logins, but OAuth tokens bypass these controls. They grant persistent trust between apps without further verification. A token acts on behalf of a user or service without needing a password, so an attacker who obtains a valid token can access the connected app's data as if they were already authenticated. There's no pop-up to re-check MFA when an OAuth token is used. As a result, without special oversight, OAuth and API tokens have become an Achilles' heel in SaaS security. Other legacy solutions, like cloud access security brokers, focus on user-to-app traffic but don't monitor these app-to-app connections.

To read the complete article see: [The Hacker News](https://thehackernews.com/2025/10/saas-breaches-start-with-tokens-what.html) 😊