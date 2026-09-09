---
title: DoppelCart Fraud Network Exposed 119,000 Fake Shops Stealing Credit Cards
date: 2026-09-08
categories: [SECURITY]
tags: [FRAUD,CYBERSECURITY,CREDIT-CARDS,FAKE-SHOPS,DOPPELCART]
---

## DoppelCart Fraud Network Exposed: 119,000 Fake Shops Stealing Credit Cards

A massive operation dubbed **"DoppelCart"** uses more than **119,000 domains** to run a network of fake e-shops that steal payment card details. Most of the domains are in the **.SHOP** top-level domain, accounting for **2.72%** of all sites on the TLD. German cybersecurity startup **Nebty** discovered DoppelCart and describes it as the largest publicly documented fake-shop cluster by domain count, far surpassing the second-largest, **"BogusBazaar,"** which operated a network of **75,000 sites** that recorded an estimated **850,000 fraudulent transactions**. The company's latest scans show that more than **105,000 DoppelCart shops** are still active. 🚨

Nebty CEO **Benedikt Scheungraber** told BleepingComputer that **96%** of the shops confirmed to be part of DoppelCart share identical build files and resolve to **27 commerce backends**. The sites impersonate legitimate businesses by copying product catalogs, descriptions, branding, and images, sometimes loading assets directly from the real company's servers. Scheungraber says that the shops mimic **44,182 different brands**, with a median of **two clones** for each. However, some brands like **SodaStream, Velasca, CurrentBody, Daniel Wellington, Dreame, Horze, MOVA,** and **SPARK PAWS** received more attention, with over **30 shops** each. The fake sites advertise big discounts of up to **65%** in many cases to lure bargain-hunting shoppers. 💸

When testing several checkout pages in the DoppelCart cluster, Nebty found code that collected sensitive information related to payment cards and their holders: **Card numbers, Expiration dates, Security codes, Cardholder names, Email addresses, Phone numbers,** and **Physical addresses**. Each data field is transmitted over **WebSockets** to the command-and-control (C2) in real time, Nebty says in a report shared with BleepingComputer. The checkout code can also relay the one-time confirmation code issued by a victim's bank, which the attackers may use to bypass security protections. Nebty says some of the fake stores show the impersonated brand's legitimate support address, leading victims who didn't receive their purchases to contact the real company. 📞

Regarding mitigation, Scheungraber says that the company tried to contact the main hosting provider for DoppelCart sites but received no response. Separately, Nebty created a searchable database to help companies identify DoppelCart impersonation and brand abuse and take appropriate action to protect themselves. 🔍

[Read full article](https://www.bleepingcomputer.com/news/security/doppelcart-fraud-network-uses-119-000-fake-shops-to-steal-credit-cards/)  
