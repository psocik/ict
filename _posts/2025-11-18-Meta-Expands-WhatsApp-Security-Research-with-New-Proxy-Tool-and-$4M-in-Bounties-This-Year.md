---
title: Meta Expands WhatsApp Security Research with New Proxy Tool and $4M in Bounties This Year
date: 2025-11-18
categories: [SECURITY]
tags: [WHATSAPP,META,SECURITY RESEARCH,BUG BOUNTY,PROXY TOOL]
---

Meta is expanding its WhatsApp security research efforts with a new proxy tool for bug bounty hunters and over $4 million in bounties awarded this year alone. The WhatsApp Research Proxy aims to facilitate deeper investigation into the platform's technologies, recognizing the application's attractiveness to state-sponsored actors and commercial spyware vendors. This initiative arrives alongside a pilot program inviting research teams to focus on platform abuse with internal engineering and tooling support, lowering the barrier for academics less familiar with traditional bug bounties.

In the last 15 years, Meta has awarded over $25 million in bug bounties to more than 1,400 researchers across 88 countries, with almost 800 valid reports receiving over $4 million this year. Notable discoveries include an incomplete validation bug in WhatsApp prior to v2.25.23.73, WhatsApp Business for iOS v2.25.23.82, and WhatsApp for Mac v2.25.23.83. These bugs could have enabled a user to trigger the processing of content retrieved from an arbitrary URL on another user's device, though there is no evidence of exploitation in the wild.

Furthermore, Meta addressed a simple WhatsApp security flaw that exposed 3.5 billion phone numbers, implementing anti-scraping protections after a report detailed a method to enumerate WhatsApp accounts at scale across 245 countries, bypassing rate-limiting restrictions. This attack exploited a legitimate contact discovery feature, allowing attackers to compile publicly accessible information, profile photos, About text, and timestamps. While Meta found no evidence of malicious abuse, the study revealed millions of phone numbers registered in countries where WhatsApp is banned, like China (2.3 million) and Myanmar (1.6 million).

Researchers have also demonstrated how delivery receipts can pose privacy risks, allowing attackers to send crafted messages to extract activity status without user knowledge. This "Careless Whisper" technique can infer a user's schedule, device usage, and even launch resource exhaustion attacks like draining battery or data. Meta emphasized ongoing efforts to enhance anti-scraping systems and confirmed that researchers securely deleted the collected data. User messages remain protected by WhatsApp’s default end-to-end encryption.

Meta also released an operating system-level patch for Quest devices to address CVE-2025-59489 (CVSS score: 8.4). This vulnerability could have allowed malicious applications to manipulate Unity applications for arbitrary code execution. Security teams should ensure Quest devices are updated to mitigate this risk.

To read the complete article see: [The Hacker News](https://thehackernews.com/2025/11/meta-expands-whatsapp-security-research.html) 

There's still time to register for RISE-Malaysia next month: [RISE-Malaysia Event](https://www.team-cymru.com/events), and the one next February in San Francisco: [RISE-USA Event](https://go.team-cymru.com/rise-usa-2026).