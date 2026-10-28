---
title: SkyW4lker Exposed A Growing Microsoft 365 Phishing Threat to American Enterprises
date: 2026-10-27
categories: [CYBERSECURITY]
tags: [MICROSOFT,PHISHING,CYBERSECURITY,SKYW4LKER]
---

## SkyW4lker Exposed: A Growing Microsoft 365 Phishing Threat to American Enterprises

**SkyW4lker** (SkyW4lker x365 Sentinel) is an active device-code phishing kit targeting Microsoft 365 users in the United States, Europe, and other regions. By abusing Microsoft's legitimate authentication process, the kit can give attackers access to corporate accounts without stealing passwords or bypassing MFA. This puts business emails, sensitive documents, and other Microsoft 365 resources at risk of unauthorized access. 🚨

The ANY.RUN team identified **618 sandbox analyses** related to SkyW4lker between June and October 21, 2026, with **46% of submissions coming from the United States**. Activity increased from 20 analyses in June to 200 in September, highlighting the growing exposure of organizations relying on Microsoft 365. These submissions were mainly by organizations in the technology, manufacturing, and government sectors, most often from the United States, India, Canada, and the United Kingdom. 🌍

SkyW4lker is distributed through phishing emails with a password-protected malicious attachment; the password is provided in the email body. After a chain of decoy pages, the victim reaches a page that asks for a Microsoft device code. The kit consists of a PHP backend and obfuscated JavaScript, with main features including IP-based geolocation of visitors and periodic polling of the backend to check whether the victim has completed authentication. SkyW4lker exploits routine business workflows, using contracts, invoices, and service proposals as phishing lures. By directing employees through familiar platforms and legitimate Microsoft authentication pages, attackers make malicious requests harder to distinguish from normal business activity. 📧

SkyW4lker shares its JavaScript modules, landing-URL format, and part of its hosting infrastructure with Gabagool, a credential phishing kit active since April 2026. Researchers assess with high confidence that both kits were built by the same developer. 🔍

[Read full article](https://any.run/cybersecurity-blog/skyw4lker-phishing-kit-analysis/) 
