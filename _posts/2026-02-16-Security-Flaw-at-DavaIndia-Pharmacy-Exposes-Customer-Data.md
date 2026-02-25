---
title: Security Flaw at DavaIndia Pharmacy Exposes Customer Data
date: 2026-02-16
categories: [SECURITY]
tags: [DAVAINDIA,SECURITY,DATA BREACH,PHARMACY]
---

## Security Flaw at DavaIndia Pharmacy Exposes Customer Data 🚨

A significant security flaw at DavaIndia Pharmacy has exposed customer data and granted unauthorized access to outsiders. DavaIndia, a prominent Indian pharmacy retail chain, is dedicated to providing affordable generic medicines. Operated by Zota Health Care Ltd., the brand aims to make healthcare more accessible across India.

### What Happened? 🔍

The vulnerability allowed unauthorized access to the platform, compromising customer order data and granting full administrative control. This weakness raised serious concerns regarding data protection and the integrity of internal systems.

Security researcher Eaton Zveare uncovered these serious flaws while analyzing the website. He discovered an exposed admin subdomain that permitted unauthenticated access to super-admin APIs. Zveare noted, "The site is developed using Next.js, so naturally there’s plenty of client-side JS to pick through. One part that stood out immediately was the forgot password code that mentioned super-admin APIs." 

### The Risks 🚧

By crafting a POST request, Zveare was able to create a new super admin account, gaining full control of the platform. With this access, he could view and edit stores, pharmacist details, customer orders, personal data, products, inventory, and even coupons. He demonstrated how a 100% discount coupon could be generated and how prescription requirements could potentially be bypassed, highlighting major risks to customer privacy and drug controls.

### Conclusion 🛡️

The flaw was reported on August 20, 2025, and was fixed within a month, although confirmation was delayed. With support from CERT-In, the case was confirmed closed on November 28, 2025, and publicly disclosed on February 13, 2026.

For more details, [Read full article](https://securityaffairs.com/188056/security/a-security-flaw-at-davaindia-pharmacy-allowed-attackers-to-access-customers-data-and-more.html)