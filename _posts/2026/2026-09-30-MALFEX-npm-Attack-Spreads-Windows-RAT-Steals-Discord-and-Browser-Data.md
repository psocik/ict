---
title: MALFEX npm Attack Spreads Windows RAT, Steals Discord and Browser Data
date: 2026-09-30
categories: [CYBERSECURITY]
tags: [MALWARE,NPM,WINDOWS,DISCORD,DATA-THEFT]
---

## MALFEX npm Attack: A Growing Threat 🚨

CloudSEK has uncovered the **MALFEX campaign**, which utilizes malicious npm packages to deploy the **Overlord RAT**. This attack not only steals Discord and browser data but also targets Windows systems. 

### What is MALFEX? 
A long-running supply-chain campaign has been identified, using malicious npm packages to deliver a remote access trojan (RAT) that steals credentials and maintains access to compromised Windows systems. The operation, dubbed **MALFEX**, has been linked to a single operator active since **August 2023**. This operator has used multiple npm accounts featuring the Malfex name, along with a GitHub account named **cavecrew**. 

### Key Findings 🔍
- Researchers found references to "Murizada" in one package's README, indicating the owner of the Malfex team.
- At least **12 npm packages** and a GitHub repository have been linked to this operation.
- Packages such as **tlxbnhd**, **tldriver**, and **mxdriver** use npm installation scripts to download a Windows executable disguised as a PNG file. This executable contains an encrypted script that ultimately loads the **Overlord RAT**.

### Overlord RAT Capabilities 
The Overlord RAT can:
- Capture screens 📸
- Record keystrokes ⌨️
- Provide remote shell access 💻
- Interact with a victim's desktop 🖥️

This version of the malware can also utilize the **Solana blockchain** to retrieve updated command-and-control (C2) server addresses, enhancing its ability to locate its control infrastructure.

### Delivery Mechanisms 📦
A second delivery chain employed **img-to-native** and its dependency **cdn-img-fetch** to retrieve a PNG file from GitHub. This package decrypted an embedded payload and eventually fetched a **64 MB Node.js bundle** that injected code into Discord clients, stealing authentication tokens and account information. It also targeted browser cookies, credentials, cryptocurrency wallets, and Telegram session data. The stolen information was sent to an attacker-controlled Discord webhook.

### Ongoing Risks ⚠️
Some malicious packages remained available long after the campaign began. Five MALFEX packages received security advisories, while three remained without advisories. Notably, **function-flag** stayed malicious and installable for **14 months**. Another package, **cdn-img-fetch**, remained available even after npm removed its parent package, **img-to-native**.

CloudSEK warns that simply removing one malicious npm package is not sufficient when related packages, dependencies, and external payloads remain active. They recommend checking connected components instead of relying solely on individual npm security advisories.

For more details, check out the full article: [Read full article](https://hackread.com/malfex-npm-windows-rat-steals-discord-browser-data/) 
