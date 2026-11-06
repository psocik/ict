---
title: The Internals of a Badbox Operation
date: 2026-11-02
categories: [CYBERSECURITY]
tags: [MALWARE,AD-FRAUD,CYBERSECURITY,RESEARCH]
---

## The Internals of a Badbox Operation

This report focuses on **MECOOL**, a pre-infected set-top box that has dominated the consumer market since early 2020. Through this investigation, Synthient's Research Team uncovered a massive campaign involving over **1.3 million compromised devices**, operating as part of a larger pay-per-install (PPI) campaign, which has had a significant impact by helping to fuel the ad fraud and proxy ecosystem. Synthient's Research Team attributed MECOOL to **Videostrong Technology Co., Ltd.**, a China-based device manufacturer, which has maintained the development of **"x.cpe,"** a backdoor. This backdoor grants operators persistent device access for deploying additional payloads including, but not limited to, **AdMoyu, Appsalt (Honeygain),** and **APSolo**. As a result, Google has cut ties with Videostrong and permanently banned the company from building and selling certified Android devices or supplying software to other certified vendors. Synthient's Research Team assesses with high confidence that Videostrong Technology Co., Ltd. is the operator behind this campaign, which spans numerous front-facing stores, including **yokatv.com**, with these devices all packaging the x.cpe backdoor.

The MECOOL KM9PRO Max comes pre-installed with a backdoor running under the name **"com.oemservice"** (hereafter referred to as **"x.cpe"**). Signed by **Skyworth Digital Technology**, the backdoor grants operators system-level privileges, allowing for everything from remote code execution to file management. Upon boot, com.oemservice sends the device information to **extstb.anyevonline.com**.

Synthient's Research Team conservatively estimates there to be at least **1.3 million backdoored devices**, with around **half a million actively online**. These findings show a strong presence in **Malaysia, Mexico,** and **Brazil**, with victims in other notable countries, including the **United States, China,** and **Germany**. Illicit pay-per-install networks provide a substantial backbone to the broader fraud ecosystem, powering everything from direct ad fraud to unregulated proxy networks that push credential stuffing and DDoS botnets. Synthient's Research Team recommends that these devices be immediately pulled from online retail stores and marketplaces. Consumers are also advised to permanently dispose of these devices, as they pose a high risk of containing additional malware. Organizations should block the full list of indicators and observables in the Indicators of Compromise section of Synthient's public research repository. Victims should identify and disconnect any unknown or suspicious smart devices on their home network. The complete indicators of compromise and observables, including file hashes, certificate fingerprints, network infrastructure, SDK identifiers, and affected device models, are available in Synthient's public research repository on GitHub.

To read the complete article see: [Read full article](https://synthient.com/blog/the-internals-of-a-badbox-operation) 
