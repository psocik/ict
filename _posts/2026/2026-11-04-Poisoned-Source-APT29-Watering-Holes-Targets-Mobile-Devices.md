---
title: Poisoned Source APT29 Watering Holes Targets Mobile Devices
date: 2026-11-04
categories: [CYBERSECURITY]
tags: [APT29,WATERING-HOLES,MOBILE-DEVICES,CYBERSECURITY,MALWARE]
---

## Poisoned Source: APT29 Watering Holes Targets Mobile Devices

In mid-October 2026, Sekoia's Threat Detection & Research (TDR) team uncovered a large-scale watering hole campaign involving the compromise or cloning of several high-profile websites in the US, Ukraine, Czech Republic, and Bulgaria. 🌍 

In parallel, the intrusion set executed a supply-chain compromise of a Ukrainian web analytics service, exposing hundreds of legitimate websites and their visitors to its exploit kit for one week. This campaign relies on three infection vectors:
- Direct JavaScript injection on legitimate websites
- Adversary-in-the-Middle-like domains
- Supply-chain compromise of the Ukrainian web analytics service

All three infection vectors deliver the same payload: a code injection that loads an external script to profile the visitor's browser and device. The delivery host then uses the mobile and browser version to serve platform-specific n-day exploit chains without user interaction. One of these chains is DarkSword, a suspected Commercial Surveillance Vendor-developed iOS exploit kit uploaded on VirusTotal in September 2026. The final payloads exfiltrate cookies or full device data from iOS devices, and Chrome data and Wi-Fi passwords from Android devices, without establishing persistence. 🔒 

Based on technical overlaps and observed operational patterns, we assess with moderate to high confidence that this campaign was conducted by APT29 (also tracked as Midnight Blizzard, Cozy Bear, or The Dukes), a Russian nexus intrusion set widely attributed to the Foreign Intelligence Service of the Russian Federation (SVR).

Our investigation began with the detection of a malicious JavaScript inclusion leading to an attacker-controlled exploit delivery server at the top of a Ukrainian gas production company. Following this, additional watering hole campaigns were identified involving both compromised legitimate websites and attacker-controlled domains. When the intrusion set was unable to compromise a legitimate website directly, they adopted an Adversary-in-the-Middle (AiTM)-like approach, registering lookalike domains and modifying their HTML content on-the-fly to inject malicious JavaScript at the bottom of each page. 

We identified two high-profile websites set up by the intrusion set to act as reverse proxies, such as america250[.]holiday for america250.org and theowo[.]club for Raffles London at The OWO. By doing this watering hole impersonating the Raffles London at The OWO, the intrusion set may have sought to target diplomatic delegations and high-profile guests through targeted spear-phishing campaigns. 🎯 

Additionally, several other websites were identified as compromised during our investigation, including those of a major industry trade association representing US companies operating in the chemical industry and a far-right European political party.

Further analysis of seemingly unrelated websites revealed a common denominator: the Plerdy SEO Tracker, a third-party component that had been compromised by the intrusion set for one week. Between 27 August and 3 September 2026, the intrusion set compromised the Ukrainian Plerdy analytics tracker hosted under the domain a.plerdy[.]com, which is loaded by thousands of websites, the large majority of them Ukrainian. 

This supply chain attack spread through high-value targets, such as army, special force, and military equipment (ballistic, UAV) websites. During this one-week campaign, the intrusion set injected malicious code into the legitimate hxxps://a.plerdy[.]com/public/js/click/main.js tracker file, causing visitors to load both the legitimate Plerdy script and the intrusion set's fingerprinting script. 

The UltimateFingerprinter script is a custom-built JavaScript payload, designed to retrieve the user's operating system and browser version to deliver the corresponding exploits and collect a detailed user device fingerprint. This script is designed to exfiltrate the visitor's browser and device configuration from 61 distinct collectors that together build 394 fields in JSON. Examples of fields collected include Classic device fields like canvas, audio, webgl, fonts, css, math, screen; Sandbox checks such as webrtc, mediaDevices, battery, sensors, network, and performance timing; and Apple specific fields like iosFeatures, macFeatures, and safariExtensions.

For more details, check out the full article: [Read full article](https://www.sekoia.com/blog/poisoned-source-apt29-watering-holes-targets-mobile-devices-with-n-day-exploits)  
