---
title: OpenRouter Drops AI Providers Over Leaked Prompts and Secrets
date: 2026-11-23
categories: [SECURITY]
tags: [OPENROUTER,AI,DATA-LEAK,SECURITY]
---

## OpenRouter Drops AI Providers Over Leaked Prompts and Secrets 🚨

OpenRouter has taken decisive action by removing three AI providers from its platform after discovering violations of their data-handling policies that exposed sensitive information. This move also led to the revocation of Zero Data Retention (ZDR) eligibility for 125 endpoints as a precautionary measure, and all potentially affected customers have been notified.

The operational technology security company Dragos alerted OpenRouter after sending two million test prompts through the platform, each containing a unique tracking link or decoy credential. They detected activity indicating that data from at least three AI providers was exposed. Dragos reported that some credentials were leaked to outsiders and used in the wild, suggesting that the test prompts had escaped.

> "We observed activity indicating that data from at least three AI providers was exposed. Our seeded test prompts were used in attempts to access our controlled test systems and canary AWS accounts," said Dragos.

OpenRouter clarified that there was no breach on its own systems, indicating that the leak originated at the provider level. Consequently, the three leaking inference providers—Together AI, Phala, and Novita—were removed from the platform. Additionally, Atlas Cloud announced it would voluntarily withdraw its models from OpenRouter pending security testing due to a third-party security incident.

Together AI acknowledged that an AI coding agent exposed a repository credential on GitHub, allowing unauthorized access to stored prompt samples from June and July involving MiniMax M3, GLM-5.2, and Kimi K2.6. Phala reported that an attacker compromised a server processing DeepSeek V4 Flash 0731 requests routed through OpenRouter between October 21 and 22, and possibly up to November 8, obtaining application credentials from affected virtual machines. Novita indicated that a routing misconfiguration forwarded some MiniMax requests, including those sent through OpenRouter, to MiniMax's official API between May 28 and November 11.

In response to these incidents, all four providers are tightening their security controls, strengthening their zero data retention or data deletion policies, and advising potentially impacted users to rotate any secrets that may have been exposed in the leaked requests. OpenRouter is also adapting Dragos' tests for ongoing use to check whether AI providers forward or leak user requests/responses to third parties and will require validation before restoring ZDR eligibility.

[Read full article](https://www.bleepingcomputer.com/news/security/openrouter-drops-ai-providers-over-leaked-prompts-and-secrets/) 
