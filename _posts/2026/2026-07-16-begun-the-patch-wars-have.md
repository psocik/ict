---
title: Begun, the Patch Wars Have
date: 2026-07-16
categories: [CYBERSECURITY]
tags: [PATCHING,VULNERABILITIES,CYBERSECURITY,MICROSOFT,MALWARE]
---

## 🚀 Begun, the Patch Wars Have

This July's Patch Tuesday is an absolute whopper! There are **622 vulnerabilities** being patched, with **62** classified as critical severity. To put this into context, this month alone has more vulnerabilities listed than all of **2018** combined! Three of these are zero days, two of which are actively exploited. Microsoft has shipped its largest Patch Tuesday on record, more than triple June's previous high of around **200**. Microsoft attributes this surge to their AI frontier-accelerated research.

We anticipated this flood of patches, but the real challenge lies in whether companies can keep up with the demand to implement these updates across their infrastructures. What might just be a hot summer for patching could evolve into a **12-month fusillade** of KEV and EPSS notifications, especially for companies already under pressure.

### 🛡️ New Threats Unveiled

Cisco Talos has disclosed a new campaign by **UAT-11795**, a sophisticated, financially motivated Russian-speaking adversary targeting users in the U.S. and Europe since at least **June 2025**. UAT-11795 utilizes trojanized software installers, including popular tools like **Webex**, **Zoom**, and **MobaXterm**, to deliver a custom Python-based remote access tool known as **Starland RAT**. This RAT serves as a gateway for deploying further malicious payloads, notably a bespoke, in-memory PowerShell command-and-control (C2) implant called the **WLDR agent**.

This opportunistic campaign casts a wide net across multiple victim profiles, turning a simple software download into a full-blown compromise. UAT-11795 employs highly evasive techniques, including AMSI and ETW bypasses, and uses a clever blockchain-anchored fallback mechanism to maintain persistent command and control. Once inside, attackers rapidly deploy secondary payloads like **CastleStealer** and **Remcos RAT** to siphon high-value credentials and cryptocurrency assets.

### ⚠️ Mitigation Strategies

To mitigate risks, educate your users on **ClickFix** social engineering tactics and the dangers of unofficial software downloads. Monitor for suspicious execution of **mshta.exe** and unusual PowerShell activity, particularly scripts executing from memory or creating unexpected scheduled tasks. Ensure endpoint detection solutions are tuned to catch in-memory execution and AMSI tampering.

Beyond the widespread patching efforts, other critical vulnerabilities have emerged, including a **RabbitMQ** security defect that impacts an open management endpoint, returning the OAuth secret to anyone without authentication. This affects RabbitMQ, a popular open-source message broker that routes, buffers, and distributes messages, enabling asynchronous communication between applications. Additionally, a two-click cursor exploit enables development environment takeover, impacting **Cursor AI**, a popular AI coding tool used by more than **50,000** enterprises and **64%** of the Fortune 500. Attackers can install permission-rich model context protocol (MCP) servers on privileged developers' machines through this exploit.

For more details, check out the full article: [Read full article](https://blog.talosintelligence.com/begun-the-patch-wars-have/)