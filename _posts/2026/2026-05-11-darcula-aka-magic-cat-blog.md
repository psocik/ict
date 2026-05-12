---
title: Darcula aka. Magic Cat - Blog
date: 2026-05-11
categories: [CYBERSECURITY]
tags: [DARCULA,PHISHING,MALWARE,CYBERSECURITY]
---

## Darcula aka. Magic Cat - Blog

The **Darcula phishing framework** continues to evolve, transitioning from early API-driven roots to a sophisticated **"Phishing-as-a-Service"** model using encrypted WebSockets and wrapper APIs. Our latest research uncovers the inner workings of Darcula, its expansion into fake e-commerce storefronts via the **"NewBee"** and **"PandaShop"** ecosystems, and its persistent targeting of government and financial institutions worldwide. This Chinese-backed operation maintains a global footprint through advanced domain rotation and localized social engineering lures. Darcula is one of the earliest large-scale Chinese-language phishing frameworks observed operating at a global scale. The platform established many of the operational patterns now commonly seen in Chinese phishing ecosystems, including API-driven phishing services, centralized infrastructure, encrypted client-server communications, and large domain rotation pools. Although several generations of the framework exist, **Darcula v3** remains active today, despite increasing competition from newer phishing services. Analysis of recent urlscan telemetry shows the framework continuing to operate across multiple domains and hosting environments.

The earliest observed Darcula deployments relied on multiple exposed HTTP API endpoints. These APIs controlled phishing page behavior and backend communications. In this earliest stage, the framework relied on: 
- HTTP APIs controlling the phishing workflow 
- WebSocket communications for backend interaction 
- Template-driven phishing page generation

These architectural decisions laid the foundation for later versions. **Darcula v2** represented a significant evolution and marked the point where the framework expanded dramatically in usage. Two major architectural changes were introduced: API consolidation into a single meta-wrapper API call, and encrypted communications between the phishing page and backend. The wrapper API pattern, now common across many Chinese phishing kits, encapsulates internal API calls inside a single externally exposed endpoint. Two distinct variants appeared in v2: U2, and MC. Both variants encrypted data using the Rabbit stream cipher, a largely obsolete symmetric cipher no longer supported by many modern encryption libraries, with the exception of CryptoJS.

**Darcula v3** represents a structural redesign while preserving key elements of earlier versions: Wrapped API architecture, WebSocket communications, and Rabbit cipher encryption. However, several operational changes were introduced that both improved the framework's flexibility and created new detection opportunities. Unlike v2, Darcula v3 uses a single static Rabbit cipher key for both requests and responses.

To read the complete article see: [Read full article](https://urlscan.io/blog/2026/05/11/CnDarcula/)