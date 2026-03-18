---
title: AppsFlyer Web SDK Hijacked to Spread Crypto-Stealing JavaScript Code
date: 2026-03-14
categories: [SECURITY]
tags: [APPSFLYER,MALWARE,CRYPTOCURRENCY,JAVASCRIPT,SECURITY]
---

## 🚨 AppsFlyer Web SDK Hijacked!

The **AppsFlyer Web SDK** was temporarily hijacked this week with malicious code used to steal cryptocurrency in a supply-chain attack. The payload can intercept cryptocurrency wallet addresses entered on websites and replace them with attacker-controlled addresses to divert funds to the threat actor. Since the AppsFlyer SDK is used by thousands of applications for marketing analytics, the impact extends to a significant number of end users. According to AppsFlyer, its SDK platform is used by **15,000 businesses worldwide** for over **100,000 mobile and web applications**.

### 🕵️‍♂️ Discovery of the Compromise

The suspected compromise was discovered by **Profero researchers**, who confirmed the presence of obfuscated attacker-controlled JavaScript being delivered to users visiting websites and applications that loaded the AppsFlyer SDK. On **March 9**, Profero discovered a malicious payload served by the SDK from its official domain, at `websdk.appsflyer.com`, which was also reported by multiple users. The injected JavaScript was designed to preserve normal SDK functionality, but in the background, it loads and decodes obfuscated strings at runtime and hooks into browser network requests. The malware monitors pages for cryptocurrency wallet input activity. When it detects a wallet address, it replaces it with the attacker’s wallet while exfiltrating the original wallet address and associated metadata. The targeted addresses include **Bitcoin, Ethereum, Solana, Ripple,** and **TRON**, covering a large swath of mainstream cryptocurrency transactions. The researchers suggest that the exposure window is likely between **March 9, 22:45 UTC**, and **March 11**.

### 🔒 AppsFlyer's Response

A spokesperson for AppsFlyer confirmed via a statement that unauthorized code was delivered through the AppsFlyer SDK. AppsFlyer detected and contained a domain registrar incident on **March 10** that temporarily exposed the AppsFlyer Web SDK running on a segment of customer websites to unauthorized code. "The mobile SDK was not affected, and our investigation to date has not identified evidence that customer data on AppsFlyer systems was accessed," AppsFlyer told BleepingComputer. The vendor said that the issue has been resolved and that AppsFlyer customers received direct communication and updates about the incident. "The mobile SDK has remained safe to use throughout the process, and the web SDK is safe to use." The company said that the investigation is ongoing and it is working with external forensic experts.

### ⚠️ Recommendations

Given the uncertainty about exactly what happened and the scope of the incident, organizations deploying the SDK should review telemetry logs for suspicious API requests from `websdk.appsflyer.com`, downgrade to known-good versions of the SDK, and investigate potential compromise.

[Read full article](https://www.bleepingcomputer.com/news/security/appsflyer-web-sdk-used-to-spread-crypto-stealer-javascript-code/)