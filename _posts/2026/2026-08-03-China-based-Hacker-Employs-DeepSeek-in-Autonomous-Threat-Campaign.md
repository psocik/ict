---
title: China-based Hacker Employs DeepSeek in Autonomous Threat Campaign
date: 2026-08-03
categories: [CYBERSECURITY]
tags: [HACKER,DEEPSEEK,AI,CYBERSECURITY,VULNERABILITIES]
---

## China-based Hacker Employs DeepSeek in Autonomous Threat Campaign 🚨

A Chinese-speaking threat actor has been identified running an AI-based hacking campaign that leveraged **DeepSeek**, using the **Hermes Agent** framework for autonomous cyber capabilities, according to a report released Thursday from Palo Alto Networks’ Unit 42.

The hacker used Hermes Agent to search for critical vulnerabilities, scanning GitHub for recently trending proofs of concept. 

The threat actor exploited China’s DeepSeek AI platform to target a **Langflow vulnerability** tracked as **CVE-2026-33017**. The attempt ultimately failed, as the vulnerability required auto login to be enabled or a public flow ID, which the hacker did not possess.

The chained attack sequence involved an arbitrary file read flaw, tracked as **CVE-2026-21858**, and a remote-code execution flaw, tracked as **CVE-2026-68613**. Although DeepSeek found potential targets, the attacks were unsuccessful due to authentication requirements.

Another manual exploitation attempt, using **CVE-2026-39987**, against **Marimo**, a reactive Python notebook, was successful.

[Read full article](https://www.cybersecuritydive.com/news/china-based-hacker-deepseek-autonomous/826784/)