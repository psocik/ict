---
title: Smart Contracts for C&C How ClearFake Hid in Plain Sight on BSC Testnet
date: 2026-05-26
categories: [CYBERSECURITY]
tags: [SMART CONTRACTS,CYBERSECURITY,CLEARFAKE,BSC,THREAT ANALYSIS]
---

## Smart Contracts for C&C: How ClearFake Hid in Plain Sight on BSC Testnet

**TrendAI™ Research** has conducted an in-depth analysis of a sophisticated intrusion where threat actors utilized the **EtherHiding** technique to deliver ClearFake payloads through smart contracts on the **BNB Smart Chain testnet**. 🚀 This attack chain culminated in the simultaneous deployment of two stealers, **SectopRAT** and **ACRStealer**, alongside an on-chain execution tracker that confirmed each victim's compromise in real-time.

### Key Findings:
- **EtherHiding** was used to store the ClearFake payload and routing instructions within BNB Smart Chain testnet smart contracts, creating an immutable infrastructure that is resistant to takedown due to the nature of blockchain technology. 
- The attack delivered two payloads: **SectopRAT**, a .NET-based RAT capable of browser session hijacking, and **ACRStealer**, a C++ infostealer, utilizing a **ClickFix** social engineering overlay with separate payloads for Windows and macOS victims based on OS detection.

### Why This Matters:
Unlike traditional command-and-control (C&C) infrastructures, this routing layer is unalterable, making it a significant challenge for security vendors and law enforcement. The ClearFake campaign has refined this technique by storing the entire payload JavaScript on-chain, ensuring that malicious code is executed in the victim's browser without the need for external hosting. 

### Operational Insights:
- The campaign's operational history was established through the deployment timeline of four distinct smart contracts, confirming that this blockchain C&C has been a long-running and actively maintained campaign.
- The oldest contract, **Smart Contract A**, was deployed on **May 26, 2025**, with subsequent contracts deployed in September 2025 and June 2025.

For more detailed insights, you can read the full article here: [Read full article](https://www.trendmicro.com/en_us/research/26/e/smart-contracts-for-command-and-control.html)