---
title: Hackers Breach Government Webmail While Running Parallel Crypto Fraud
date: 2026-08-13
categories: [CYBERSECURITY]
tags: [HACKERS,GOVERNMENT,CRYPTO,FRAUD,CYBERSECURITY]
---

## Hackers Breach Government Webmail While Running Parallel Crypto Fraud 🚨

The **Jewelbug hacker group** has been conducting espionage operations targeting governments and militaries while simultaneously engaging in cryptocurrency fraud. This group has targeted critical sectors such as defense, telecommunications, education, and aviation, indicating they may also operate as a hack-for-hire organization seeking profit from cybercrime.

In a recent operation, Jewelbug compromised webmail accounts belonging to **15 government tenants** as part of a campaign targeting a country in the Middle East. Researchers at **Symantec** discovered that both the espionage campaign and the cryptocurrency fraud were managed from the same control panel.

### Attack Methodology 🔍

The China-based hacker group gained write access to the shared webmail installation and inserted a malicious script into its common template. This script executed on login pages and mailbox views across the 15 tenants. Upon execution, it established a **WebSocket connection** to the attacker's command-and-control (C2) server, exfiltrating webmail cookies and retrieving the user's email address to check if it belonged to a targeted government domain.

Valuable targets received a fake **Adobe Flash update** prompt, which installed the main payload on Windows: the **Antino backdoor** and browser tooling. Additionally, the threat actor utilizes the **XG-Web remote-access** and data-theft framework for managing campaigns and victim information. One of the payloads includes a malicious browser extension for Chrome and Firefox, named **PDF Viewer**, which steals cookies and credentials, intercepts traffic, injects JavaScript, and remotely exposes browser functions.

### Victim Database 📊

Symantec researchers noted that Jewelbug's victim database contains:
- Over **1 million implant check-in rows**
- More than **580,000 stolen browser cookies**
- Several thousand captured credentials
- Over **2,300 exfiltrated email bodies**

The espionage efforts targeted government and military organizations across the **Middle East**, **Southeast Asia**, and **South Asia**. The cryptocurrency theft operations are supported by AI-generated articles driving traffic to fake crypto exchange sites and click-fraud bots that manipulate search rankings. Researchers indicate that the threat actor relies on an automated attack pipeline that scrapes keywords, generates thousands of fake download pages using AI, and publishes them across a **44-server content-management fleet** and hundreds of lookalike domains impersonating **OKX** and **Binance**.

Jewelbug also employs a **Rust-based implant** called 'ClientKing' that targets Linux servers, ARM64 devices, and ASUS routers, supporting command execution, SOCKS proxying, DNS tunneling, and in-memory kernel module loading.

For more details, [Read full article](https://www.bleepingcomputer.com/news/security/hackers-breach-govt-webmail-while-running-parallel-crypto-fraud/)