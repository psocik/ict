---
title: SplitVPN Data Breach Exposes 865k Users' Personal Records
date: 2026-08-02
categories: [CYBERSECURITY]
tags: [DATA BREACH,VPN,PRIVACY,SECURITY]
---

## SplitVPN Data Breach Exposes 865k Users' Personal Records 🚨

A significant data breach has hit **SplitVPN**, a Russian VPN provider formerly known as NotVPN, exposing the personal records of roughly **865,000 unique users**. The incident, which occurred in **July 2026**, has raised fresh concerns about the reliability of "no-logs" promises made by privacy-focused services, since the exposed data reveals far more retention than the company publicly claimed.

In July 2026, SplitVPN suffered a breach that led to the exposure of millions of customer records, including **865,300 unique email addresses**. According to breach-tracking service **Have I Been Pwned**, the incident occurred on **July 21, 2026**, and the compromised dataset was added to its database on **August 1, 2026**, confirming **865,336 affected accounts**.

The wider breach reportedly stemmed from a **17 GB SQL database** that a threat actor began distributing on the cybercrime forum **Altenen**, claiming it was stolen directly from SplitVPN's infrastructure. Security researchers from **Mysterium** later obtained and verified the dump, confirming it contained approximately **23.4 million user records**, **13.6 million device records**, and **2.6 million payment records**, alongside nearly **58 million connection logs**. 

Beyond the headline email figure, the exposed dataset includes users' **IP addresses**, their **country of residence**, and partial **payment card information** limited to the first six and last four digits, along with the card's expiry date. Notably, full credit card numbers were not exposed, since payment data in the database was masked down to the bank identification number and last four digits.

What makes this breach particularly damaging is that SplitVPN, under its earlier NotVPN branding, explicitly advertised a **"No logs or history" policy** with a **"100% privacy guaranteed" promise**. 

Yet the leaked database reportedly contained a table tracking device-to-server connections, logging almost **58 million entries** spanning from **June 2025 through July 21, 2026**, the very day the breach dump was dated. These logs did not capture browsing destinations or visited websites, but they did link specific devices and accounts to particular VPN servers at exact timestamps, undermining the anonymity users expected.

The affected user base is reportedly concentrated in countries including **Russia, Iran, India, and Myanmar**, regions where VPN usage is often tied to circumventing state internet censorship. This geographic concentration raises the stakes considerably, as exposed connection metadata could potentially expose individuals who relied on the service to bypass government surveillance or restrictions.

Anyone who used NotVPN or SplitVPN should treat their associated email address and IP address as compromised. Security experts recommend changing any reused passwords immediately, enabling two-factor authentication wherever possible, and closely monitoring payment statements for unfamiliar charges. Users should also remain cautious of phishing attempts that reference their VPN usage, since attackers could exploit the leaked account data to craft convincing, targeted social engineering messages.

Given the breach's scale and the sensitive nature of VPN usage data, affected users should check their exposure status through breach-notification services like **Have I Been Pwned**.

[Read full article](https://cybersecuritynews.com/splitvpn-data-breach/)