---
title: QuickLens Chrome Extension Steals Crypto and Shows ClickFix Attack
date: 2026-02-28
categories: [SECURITY]
tags: [CHROME,MALWARE,CRYPTO,SECURITY]
---

## QuickLens Chrome Extension Steals Crypto and Shows ClickFix Attack 🚨

A Chrome extension named **"QuickLens - Search Screen with Google Lens"** has been removed from the Chrome Web Store after it was compromised to push malware and attempt to steal crypto from thousands of users. The extension grew to roughly 7,000 users and, at one point, received a featured badge from Google. However, on **February 17, 2026**, a new version 5.8 was released that contained malicious scripts introducing ClickFix attacks and info-stealing functionality for those using the extension.

### What Happened? 🤔
Security researchers at Annex first reported that the extension had recently changed ownership after being listed for sale on ExtensionHub, a marketplace where developers sell browser extensions. Annex states that on **February 1, 2026**, the owner changed to support@doodlebuggle.top under "LLC Quick Lens." Just over two weeks later, the malicious update was pushed to users.

Annex's analysis shows that version 5.8 requested new browser permissions, including `declarativeNetRequestWithHostAccess` and `webRequest`. It also included a `rules.json` file that stripped browser security headers, such as **Content-Security-Policy (CSP)**, **X-Frame-Options**, and **X-XSS-Protection**, from all pages and frames. The update introduced communication with a command-and-control (C2) server at **api.extensionanalyticspro[.]top**.

### The Malicious Payloads 💻
According to Annex, the extension generated a persistent UUID, fingerprinted the victim's country using Cloudflare's trace endpoint, identified the browser and OS, and polled the C2 server every five minutes for instructions.

BleepingComputer's analysis of the extension showed it connected to a C2 server at [https://api.extensionanalyticspro[.]top/extensions/callback?uuid=[uuid]&extension=kdenlnncndfnhkognokgfpabgkgehoddto](https://api.extensionanalyticspro[.]top/extensions/callback?uuid=[uuid]&extension=kdenlnncndfnhkognokgfpabgkgehoddto), where it received an array of malicious JavaScript scripts. These payloads were executed on every page load using a technique described as a **"1x1 GIF pixel onload trick."**

### User Impact ⚠️
Because the extension stripped CSP headers on all visited sites, this inline JavaScript execution worked even on sites that would normally block it. The first payload contacts **google-update[.]icu**, where it receives an additional payload that displays a fake Google Update prompt. Clicking the update button would display a ClickFix attack, prompting users to perform a verification by running code on their computers. For Windows users, this led to the download of a malicious executable named **"googleupdate.exe"** that was signed with a certificate from **"Hubei Da'e Zhidao Food Technology Co., Ltd."** Upon execution, the malware launched a hidden PowerShell command that connected to **drivers[.]solutions/META-INF/xuoa.sys** using a custom **"Katzilla"** user agent.

Another malicious JavaScript "agent" delivered by the C2 was used to steal cryptocurrency wallets and credentials. The extension would detect if **MetaMask**, **Phantom**, **Coinbase Wallet**, **Trust Wallet**, **Solflare**, **Backpack**, **Brave Wallet**, **Exodus**, **Binance Chain Wallet**, **WalletConnect**, and the **Argon** crypto wallets were installed. If so, it would attempt to steal activity and seed phrases, which would be used to hijack wallets and steal their assets. Additional payloads were used to scrape Gmail inbox contents, extract Facebook Business Manager advertising account data, and collect YouTube channel information.

### What Should Users Do? 🔍
Google has since removed QuickLens from the Chrome Web Store, and Chrome now automatically disables it for affected users. Users who installed **QuickLens - Search Screen with Google Lens** should ensure the extension is fully removed, scan their device for malware, and reset passwords for any credentials stored in the browser. If you use any of the mentioned cryptocurrency wallets, you should transfer your funds to a new wallet.

To read the complete article see: [Read full article](https://www.bleepingcomputer.com/news/security/quicklens-chrome-extension-steals-crypto-shows-clickfix-attack/)