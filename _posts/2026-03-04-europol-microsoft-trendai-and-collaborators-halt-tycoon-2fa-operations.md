---
title: Europol, Microsoft, TrendAI™ and Collaborators Halt Tycoon 2FA Operations
date: 2026-03-04
categories: [CYBERSECURITY]
tags: [EUROPOL,MICROSOFT,TRENDAI,CYBERSECURITY,PHISHING]
---

## Europol, Microsoft, TrendAI™ and Collaborators Halt Tycoon 2FA Operations 🚨

The operations of the phishing-as-a-service (PhaaS) platform **Tycoon 2FA** were taken offline this week through a combined effort of law enforcement, including **Europol**, and partner agencies, alongside private industry organizations such as **CloudFlare**, **Coinbase**, **Crowell**, **eSentire**, **Health-ISAC**, **Intel471**, **Microsoft**, **Proofpoint**, **Resecurity**, **The Shadowserver Foundation**, **SpyCloud**, and **TrendAI™**.

Tycoon 2FA first appeared in **August 2023** as a PhaaS kit designed to bypass multi-factor authentication (MFA). This platform not only steals usernames and passwords but also employs an adversary-in-the-middle (AitM) proxy that captures credentials, MFA codes, and session cookies in real-time. Attackers can then replay these session cookies to take over accounts, even when MFA is enabled.

As of now, the PhaaS platform has approximately **2,000 users** and has utilized over **24,000 domains** since its inception. It has been reported that Tycoon 2FA has been involved in large-scale campaigns targeting **Microsoft 365** and **Google**. The subscription model offered by this service lowers the barrier for criminals, eliminating the need to build infrastructure or develop tools, making it accessible even for low-skill attackers.

Newer versions of Tycoon 2FA have introduced simple evasion features to deter bots and complicate analysis, making detection and takedown efforts increasingly challenging. These modifications reflect a broader trend where phishing kits are becoming cheaper and easier to operate.

The operations of Tycoon 2FA underscore the vulnerabilities of traditional MFA without phishing-resistant protections. The cascading impact of PhaaS campaigns can extend well beyond the original victim, as stolen sessions and accounts can be reused, resold, and repurposed. Credentials and session cookies harvested through AitM campaigns can be sold in established credential marketplaces or passed to access brokers, who specialize in monetizing footholds into corporate environments.

Researchers from **TrendAI™** have been diligently tracking the infrastructure and behaviors linked to Tycoon 2FA to gain insights into its operations. By **November 2025**, they had gathered sufficient data to associate the operation with individuals using the aliases **“SaaadFridi”** and **“Mr_Xaad”**, likely the developers/operators of Tycoon 2FA. 

Disruption at this scale necessitates coordination between private sector teams who observe the technical indicators and public sector partners who possess the authority to act. A collaborative effort to track, analyze, and disrupt these operations makes it more difficult for them to rebuild and reuse tools or transition to new platforms without detection in the short to medium term.

A splash screen was served to all criminal customers of the service, confirming the seizure of the Tycoon 2FA infrastructure.

[Read full article](https://www.trendmicro.com/en_us/research/26/c/tycoon2fa-takedown.html)