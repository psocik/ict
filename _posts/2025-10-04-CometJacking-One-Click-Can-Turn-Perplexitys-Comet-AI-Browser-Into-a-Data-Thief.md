---
title: CometJacking One Click Can Turn Perplexity's Comet AI Browser Into a Data Thief
date: 2025-10-04
categories: [CYBERSECURITY]
tags: [COMETJACKING,PERPLEXITY,AI,CYBERSECURITY,DATA THEFT]
---

Cybersecurity researchers have disclosed details of a new attack called **CometJacking** targeting Perplexity's agentic AI browser Comet by embedding malicious prompts within a seemingly innocuous link to siphon sensitive data, including from connected services, like email and calendar.

The attack, in a nutshell, hijacks the AI assistant embedded in the browser to steal data, all while bypassing Perplexity's data protections using trivial Base64-encoding tricks. The attack does not include any credential theft component because the browser already has authorized access to Gmail, Calendar, and other connected services.

It takes place over five steps, activating when a victim clicks on a specially crafted URL, either sent in a phishing email or present in a web page. Instead of taking the user to the "intended" destination, the URL instructs the Comet browser's AI to execute a hidden prompt that captures the user's data from, say, Gmail, obfuscates it using Base64-encoding, and transmits the information to an endpoint under the attacker's control.

The crafted URL is a query string directed at the Comet AI browser, with the malicious instruction added using the "collection" parameter of the URL, causing the agent to consult its memory rather than perform a live web search.

To read the complete article see: [The Hacker News](https://thehackernews.com/2025/10/cometjacking-one-click-can-turn.html).