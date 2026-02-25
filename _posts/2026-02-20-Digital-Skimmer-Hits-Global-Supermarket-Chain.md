---
title: Digital Skimmer Hits Global Supermarket Chain
date: 2026-02-20
categories: [CYBERSECURITY]
tags: [DIGITAL SKIMMER,CYBERSECURITY,ECOMMERCE,DATA BREACH]
---

## Digital Skimmer Hits Global Supermarket Chain 🚨

Sansec has discovered a **payment skimmer** on the online store of a top-10 global supermarket chain. Despite repeated attempts to alert the company, the skimmer remains active after **4 days**. The affected company, with about **€100 billion** in annual revenue and over **10,000 stores** across **25 countries**, operates some of its eCommerce on the **PrestaShop** platform. As of publication, the skimmer has been active since **February 16th**. This marks the second time in just over a month that Sansec has identified a major global brand being targeted by digital skimming.

### How the Attack Works 🛡️

The attack utilizes two components: a seemingly off-the-shelf skimmer framework integrated with four popular eCommerce platforms, and a carefully localized fake payment form. This fraud technique, known as **"double-tap skimming"**, tricks customers into entering their card details into a fake form before they see the real payment form, leading them to unknowingly complete their order while their data is stolen.

**PCI-DSS** mandates that merchants redirect customers to secure payment forms managed by their payment provider, making double-tap skimming a favored method among cybercriminals. With the help of generative AI, attackers can quickly create localized payment overlays in any language and style.

### The Broader Context 🌍

This breach is part of a larger wave of attacks targeting PrestaShop stores. In **January 2026**, PrestaShop issued a security alert urging merchants to inspect their stores for skimmers injected into theme template files.

### Technical Details 🔍

The skimmer's codebase features a reusable framework likely sold or operated as a service. Before activation, it conducts admin detection routines for four CMS platforms. If any admin indicators are found, the script aborts. The skimmer activates only on checkout pages, using **localStorage** to track state and prevent double-firing. It monitors every input, select, and textarea on the page, capturing values stored with a **mn_** prefix. Card data is saved under keys like **cardNum**, **exp**, and **cvv**. Upon checkout, the skimmer validates the card number, builds a JSON payload with card data, billing info, and browser user agent, then Base64-encodes and sends it via GET to a disguised analytics endpoint.

Sansec has notified the affected company **six times** since February 16th, 2026, through various channels, including the general contact email and a direct message to the company CISO on LinkedIn. As of publication, there has been no response, and the skimmer remains active. The lack of responsive security contacts at large organizations is a systemic issue that incurs significant costs.

**Run malware & security software** that integrates with your eCommerce platform to protect against such threats.

[Read full article](https://sansec.io/research/global-retailer-prestashop-hacked)