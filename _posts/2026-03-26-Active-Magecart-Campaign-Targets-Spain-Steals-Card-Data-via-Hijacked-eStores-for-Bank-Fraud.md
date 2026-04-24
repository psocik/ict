---
title: Active Magecart Campaign Targets Spain, Steals Card Data via Hijacked eStores for Bank Fraud
date: 2026-03-26
categories: [CYBERSECURITY]
tags: [MAGECART,BANK FRAUD,CYBERSECURITY,ECOMMERCE,SPAIN]
---

## Active Magecart Campaign Targets Spain 🚨

A large-scale Magecart operation has been active for over 24 months, leveraging an infrastructure of 100+ domains. While the targeted victims are e-commerce websites, the actual pressure falls on banks and payment systems. As ANY.RUN's analysis shows, threat actors applied multi-step checkout hijacking, payment page mimicry, and WebSocket-based exfiltration of card data. This campaign demonstrates long-term persistence, supported by highly resilient infrastructure. Banks (not merchants) bear the primary impact, as stolen card data leads to fraud losses and reputational risk. The use of WebSocket exfiltration reduces visibility in traditional security monitoring tools. 

### Global Impact 🌍

This campaign is global but regionally tailored, leveraging localized payment ecosystems to enhance credibility. A total of 17 WooCommerce websites were infected between February 2024 and April 2025 and are likely linked to this campaign. The geographic scope is global, with victims from at least 12 countries, including the United Kingdom and Denmark. However, there's a notable concentration of such incidents in Spain, France, and the United States. From an industry perspective, mostly retail e-commerce companies were targeted.

### Technical Insights 🔍

The campaign's durability stems from several factors, including payment mimicry, multi-stage delivery architecture, and dynamic payload delivery. A significant portion of the infrastructure is registered via NICENIC INTERNATIONAL GROUP and disguised as legitimate web services. The injected JavaScript contains only a minor obfuscated loader that connects to external infrastructure, receives configuration data, and loads the next stage. This loader uses a fallback mechanism, iterating through backup domains until a valid response is received, allowing the campaign to continue even if some components get blocked.

Following the compromise of a website, attackers modify one of the site's embedded JavaScript files with a small, obfuscated loader. This loader executes in the victim's browser, receiving parameters for the next stage from external infrastructure, including a JSON configuration featuring the next stage's address and WebSocket/C2 server address. The primary malicious payload is then loaded into the page, potentially from rotating domains such as jquerybootstrap[.]com, newassetspro[.]com, assetsbundle[.]com, and bundlefeedback[.]com. After loading, the main payload monitors the opening of the payment step, then replaces or overlays the legitimate payment interface and injects its own elements to hide real payment confirmation.

### Conclusion 🛡️

In one analyzed case, WebSocket was the primary channel for card data exfiltration, with the C2 server disguised as redsysgate[.]com. Attackers embed exfiltration into a seemingly legitimate payment context. 

To read the complete article see:
[Read full article](https://any.run/cybersecurity-blog/banks-magecart-campaign/)