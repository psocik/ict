---
title: AI Supply Chain Security What Canary Tokens Found
date: 2026-11-19
categories: [SECURITY]
tags: [AI,SUPPLY-CHAIN,SECURITY,CANARY-TOKENS]
---

## AI Supply Chain Security: What Canary Tokens Found

We sent nearly two million AI prompts containing unique, trackable secrets to AI providers, then watched where those secrets surfaced. What we found revealed security breaches, prompt theft, and widespread failures to protect customer data. 🚨

Over a five-month period from July through November 2026, we submitted approximately two million prompts containing unique URLs and canary token credentials to widely used AI services and monitored what happened after inference. Our investigation uncovered three significant findings:

- **Evidence of provider compromises.** We observed activity indicating that data from at least three AI providers was exposed. Our seeded test prompts were used in attempts to access our controlled test systems and canary AWS accounts.
- **Unauthorized access to customer prompts by inference marketplace providers.** Multiple resellers operating through an AI inference marketplace were able to view and retain customer prompts using standard logging capabilities, without exploiting a vulnerability or bypassing platform controls.
- **Failures in privacy and data-handling practices.** We observed multiple cases in which providers appeared not to honor customer privacy settings or published policies. Examples included prompts submitted to U.S.-based providers being transmitted to Chinese AI organizations, unique URLs being accessed months after a single inference request, and one seeded link ultimately appearing in an internal company chat in China.

The results exposed a fundamental disconnect between how AI services are marketed and how inference data is handled in practice. AI providers commonly store prompts and responses for operational, training, safety, abuse-monitoring, or business purposes. This data may be retained indefinitely and can traverse multiple organizations. The inference data itself is often more valuable, frequently containing confidential source code, internal communications, strategic plans, customer information, and credentials. Providers offer privacy controls like Zero Data Retention (ZDR), but the reality is that providers often ignore these settings, making prompts not covered by ZDR fair game for resale.

The most serious finding was that attackers were actively stealing data from three different hosting providers. Incidents date back to July; none of the providers knew about their breach until we notified them. The largest breach involved a couple hundred of our AWS keys. Some stolen keys came from requests rejected before a model ever ran, indicating copying at the provider's front door. In other breaches, some stolen requests were marked as ZDR. Once attackers had credentials, they tested keys, listed S3 buckets, searched Secrets Manager and Parameter Store, and enabled AWS Bedrock models to create API keys and add IAM users. Our bait keys were used for tens of thousands of AWS API calls. One adversary compromised two providers simultaneously. The attacker's tooling evolved, ultimately including the AWS CLI on Kali Linux. On November 1, the same attacker added ARTEX, an LLM-driven penetration testing framework. Its user agents, artex-agent and artex-judge-r121, are worth adding to your detections, as both Kali and ARTEX showed up in AWS CloudTrail user agents.

Regarding the second finding, marketplace sellers viewed and retained customer prompts by simply enabling request logging. These were individuals on home internet connections attempting to access our canary servers; for instance, an attacker from France used passwords from our prompts to attempt root SSH logins. For the third finding, secret URLs in our prompts were scraped and referenced git repositories targeted for cloning, often by companies never intended to see the prompt and in conflict with privacy settings. A Chinese AI lab, for example, fetched secret URLs from over half of our prompts, including two-thirds of requests marked as ZDR.

[Read full article](https://www.dragos.com/blog/ai-supply-chain-security-canary-tokens)