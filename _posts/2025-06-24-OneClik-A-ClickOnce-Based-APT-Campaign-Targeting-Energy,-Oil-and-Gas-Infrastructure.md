---
title: OneClik A ClickOnce-Based APT Campaign Targeting Energy, Oil and Gas Infrastructure
date: 2025-06-24
categories: [NEWS]
tags: [APT,CYBERSECURITY,THREATS]
---

The Trellix Advanced Research Center has uncovered a sophisticated APT malware campaign that we’ve dubbed OneClik. It specifically targets the energy, oil, and gas sector through phishing attacks and the exploitation of Microsoft ClickOnce. The campaign exhibits characteristics aligned with Chinese-affiliated threat actors, though attribution remains cautious. Its methods reflect a broader shift toward “living off the land” tactics, blending malicious operations within cloud and enterprise tooling to evade traditional detection mechanisms.

This stealthy operation unfolds across three distinct variants (v1a,BPI-MDM, and v1d), each using a .NET-based loader ("OneClikNet") to deploy a sophisticated Golanguage backdoor ("RunnerBeacon") that communicates with threat actor infrastructure hidden behind legitimate AWS cloud services (CloudFront, API Gateway, Lambda). This makes network-based detection nearly impossible without decryption or deep behavioral analysis.

Our analysis reveals how this campaign has progressively evolved with advanced evasion tactics and C2 obfuscation across each variant. Key findings include abuse of ClickOnce to proxy execution, early injection via .NET AppDomainManager hijacking, and anti-analysis measures (anti-debugging loops and sandbox detection).

To read the complete article see:
[Complete Article](https://www.trellix.com/blogs/research/oneclik-a-clickonce-based-apt-campaign-targeting-energy-oil-and-gas-infrastructure/) 
