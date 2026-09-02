---
title: Financially Motivated Threat Actor BREEZE COMET Targets Brazil
date: 2026-09-01
categories: [CYBERSECURITY]
tags: [BREEZE COMET,CYBERSECURITY,MALWARE,BRAZIL,THREAT ACTOR]
---

## Financially Motivated Threat Actor BREEZE COMET Targets Brazil

🚨 **Overview**  
Beginning in 2024, Mandiant investigated a series of compromises affecting Brazilian financial services, retail, and eCommerce organizations. The Google Threat Intelligence Group (GTIG) tracks this activity as **BREEZE COMET** (formerly UNC5669), a financially motivated threat actor specializing in manipulating payment systems and banking software in Brazil to conduct fraudulent transfers. This activity overlaps with operations publicly reported as **Plump Spider** and **SHADOW-AETHER-064**.

🌍 **Expansion Intent**  
BREEZE COMET's operational infrastructure may indicate an intent to expand their footprint to other countries in Latin America and Africa. Additionally, there is evidence that BREEZE COMET is using generative artificial intelligence (AI) to support malware development, potentially increasing the scale, speed, and sophistication of their operations in the future.

💰 **Targeted Organizations**  
BREEZE COMET operations target organizations with permission to conduct transactions through banking software, APIs, and payment systems such as **Pix**, **STR**, and **Boleto**. This typically includes banks, payment processors, retailers, exchanges, as well as fintech and banking software providers.

🔍 **Methods of Access**  
To achieve their objective of conducting fraudulent transfers, BREEZE COMET must maintain access to the National Financial System Network (Rede Nacional do Setor Financeiro, RSFN) through an entity with this access, and access to mTLS credentials that allow sending authenticated payloads with transactional orders to Pix and STR.

🛠️ **Initial Access Techniques**  
BREEZE COMET has used various methods for initial access. In early compromises, Mandiant observed this threat actor using password spraying and voice calls impersonating IT support teams to convince users to install Remote Monitoring and Management (RMM) tools such as **AnyDesk**. In mid-2025, GTIG observed BREEZE COMET using compromised Brazilian small government websites to stage RMM tools, infostealers disguised as legitimate tax or receipt documents, or backdoors such as **XWORM**.

🔒 **Advanced Techniques**  
BREEZE COMET specifically targets development and cloud environments to escalate privileges. They deploy specialized routing malware, **COBALTSPIN**, which operates as a lightweight, evasive network tunneler, used to maintain persistent network access to financial API infrastructure.

🔑 **Backdoors and Persistence**  
In 2025 and 2026, Mandiant identified multiple backdoors that BREEZE COMET developed to establish redundant access and expand their foothold in targeted environments. These include **LIGHTPAINT**, **MILDFROST**, **KICKPLATE**, and **BOATBEAM**. To ensure these persistence mechanisms survive, BREEZE COMET actively impairs endpoint defenses.

📊 **Conclusion**  
Telemetry confirms the threat actors executing direct PowerShell commands to disable Windows Defender's real-time monitoring across compromised hosts. Furthermore, Mandiant identified evidence that BREEZE COMET used large language models (LLMs) to accelerate the creation of custom scripts for network reconnaissance, credential validation, mass deployment, victim-specific pivoting, and data extraction.

[Read full article](https://cloud.google.com/blog/topics/threat-intelligence/financially-motivated-threat-actor-breeze-comet-targets-brazil/) 