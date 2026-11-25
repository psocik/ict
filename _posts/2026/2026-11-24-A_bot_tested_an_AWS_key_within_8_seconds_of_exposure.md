---
title: A bot tested an AWS key within 8 seconds of exposure
date: 2026-11-24
categories: [SECURITY]
tags: [AWS,CLOUD,SECURITY,RESEARCH,BOTS]
---

## A bot tested an AWS key within 8 seconds of exposure 🚀

Researchers at Stony Brook University discovered that it only took a bot 7.86 seconds to test a cloud access key that was intentionally left in a publicly available software package. This highlights a significant risk: you don’t need a company cloud account to have a key worth stealing. If you’ve created an API key for an AI service and used it in an app or script, anyone who obtains it can rack up charges on your account. OpenAI warns that they could also exhaust your quota and disrupt your service.

To investigate who was collecting these secrets, Billy Tsouvalas and Nick Nikiforakis set up honeypots—decoys that allow researchers to monitor what happens when someone takes the bait. Over four months, they published 300 honeypot images across eight public registries, including working access keys for Amazon Web Services (AWS), OpenAI, and Anthropic. Each key was monitored, so any usage would be recorded in the provider's logs. Despite not advertising the images, they were downloaded tens of thousands of times. Most early activity appeared to be bots checking whether the keys were functional. Nearly every bot that tested an AWS key began with a `GetCallerIdentity` request, essentially asking, "Who am I?" This check reveals whether a key is live. About half of the IP addresses that scanned for AWS keys stopped after this initial check, while only around 6% continued to use account resources.

A key that passes this check can still be sold or used later. In tests involving AI services, OpenAI keys remained dormant for weeks before someone used one to deplete the remaining balance in under 24 hours. The researchers speculated that this waiting period reflects validated keys being resold and held idle until a buyer eventually uses them. They loaded about $60 in total onto their OpenAI and Anthropic accounts, which attackers completely drained.

The speed and number of probing bots is a concern for developers. If you use cloud or AI services, here are some precautions to help keep your keys safe:
- **Keep secrets out of shared code**: Avoid placing keys in code, public repositories, or container images.
- **Scan before you publish**: A bot can find an exposed key within seconds, so checking after publication is too late.
- **Limit key permissions**: In the second round of tests, every OpenAI and Anthropic key used by attackers had unrestricted permissions. No restricted key was exploited in this manner. Scanners seem to check permissions first, so a narrowly scoped key offers less for attackers to exploit.
- **Prefer short-lived credentials**: AWS recommends using temporary credentials instead of long-term access keys whenever possible.
- **Set spending limits and alerts**: If you’ve already published a key, treat it as compromised, even if it was public for only a minute. Revoke it, replace it, and review account activity and charges.

[Read full article](https://www.malwarebytes.com/blog/ai/2026/11/a-bot-tested-an-aws-key-within-8-seconds-of-exposure)