---
title: Researchers Identify AliExpress Phishing Domains Before Registration
date: 2026-09-25
categories: [CYBERSECURITY]
tags: [PHISHING,SECURITY,ALIEXPRESS,DOMAINS]
---

## Researchers Identify AliExpress Phishing Domains Before Registration

Security researchers have reported flagging 10 web addresses weeks before they were registered, then watching them go live as entry points to an AliExpress-themed phishing site. EfficientIP Research Labs said it identified the potential .cyou domains on June 9 in customer DNS traffic using its AI-driven domain generation algorithm (DGA) detection engine and added them to its DNS threat intelligence feed. They were subsequently registered and began resolving to IP addresses on July 2. Tracing their DNS and redirect activity led researchers to a fake AliExpress site.

All 10 domains followed the same format of one digit and five lowercase letters, shared a registration date, and resolved to three IP addresses in one subnet. EfficientIP called them DGA-style, but said the pattern alone does not prove a domain generation algorithm produced them. None hosted the lure. Each sent visitors through a tracking layer carrying campaign, click, or affiliate parameters, which EfficientIP said lets an operator replace exposed domains without rebuilding the campaign. Because such domains have little history, EfficientIP said, reputation-based controls may not yet have classified them when the first visitors arrive. The .cyou top-level domain adds context rather than proof. EfficientIP cited Cloudflare research which found that 62% of emails from .cyou in 2023 were malicious, while stressing that the ending alone does not make a site dangerous.

The chain ended at a site using a zero in place of the "o" in "shop," promoting a browser extension styled after Alitools, a legitimate shopping-assistant brand. It claims more than 500,000 users and urges visitors to click "Add to Browser." EfficientIP said visitors risked credential and payment theft and exposure of browsing activity through the extension, while the tracking parameters could earn the operator affiliate revenue. Christophe Girard, cyber AI & big data R&D manager at EfficientIP, told Infosecurity, "We cannot confirm how many individual people reached the final site, but we can confirm that it was accessed by users across eight different telecom operators in multiple geographies."

EfficientIP advised blocking the domains and IP addresses and searching DNS and proxy logs for past connections. Where users engaged with the site, it recommended resetting credentials, contacting card issuers, and removing the extension.

[Read full article](https://www.infosecurity-magazine.com/news/aliexpress-phishing-flagged-early/)\n