---
title: Sailor Framework - Chinese Backed Phishing Services
date: 2026-05-06
categories: [CYBERSECURITY]
tags: [PHISHING,CYBERSECURITY,MALWARE,THREAT-RESEARCH]
---

## Sailor Framework - Chinese Backed Phishing Services

**Overview:** 🚨

The "Sailor Framework" represents a sophisticated phishing service backed by Chinese actors, as reported by the urlscan Threat Research Team. This modular phishing platform primarily targets US state and local government entities, indicating highly localized phishing campaigns across the United States. The focus on tolling and transport infrastructure suggests a prevalent use of phishing lures related to road charges and fines.

**Key Features:** 🔑
- Government impersonation is a common theme, often combined with urgent pretexts such as fines, violations, or unpaid tolls.
- The framework supports telecom providers to enhance identity verification and billing-related phishing flows.
- It includes financial and payment brands to facilitate credential harvesting and fraudulent transactions.

**Architecture:** 🏗️

The Sailor Framework consists of multiple branches that share a common architectural foundation but differ in implementation details. Analysis indicates that minor components are modified, suggesting that the controlling threat actor can update specific parts of the framework without redeploying the entire codebase. Key characteristics include:
- Encrypted local storage
- AES-encrypted WebSocket communications
- Heavily obfuscated JavaScript for managing victim interactions and data exfiltration.

**Branch Analysis:** 🔍

The most extensively observed branch, "Sailors," serves as the baseline for the Sailor Framework, utilizing a primary storage key `ab331e7aeff3e8576b9d74971ab1a023 = sailors_config`. This branch communicates with its backend using WebSockets, with messages exchanged over this channel also being AES encrypted. 

Another branch, "t_config," aligns closely with "Sailors" but introduces updated storage naming conventions. A third branch, "globalConfig," diverges more significantly, using a different WebSocket endpoint and lacking a UUID parameter. Despite these differences, the similarities suggest a shared development origin.

**Conclusion:** 🏁

The Sailor Framework represents an evolution in phishing kit design, emphasizing modular architecture, encrypted client-side state, and WebSocket-based exfiltration. The introduction of new branches indicates active development and iterative refinement, complicating detection and clustering efforts.

To read the complete article see: [Read full article](https://urlscan.io/blog/2026/05/04/CnSailor/)