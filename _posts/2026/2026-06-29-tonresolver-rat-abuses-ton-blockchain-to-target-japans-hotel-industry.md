---
title: TONResolver RAT Abuses TON Blockchain to Target Japan's Hotel Industry
date: 2026-06-29
categories: [CYBERSECURITY]
tags: [MALWARE,PHISHING,HOTEL INDUSTRY,JAPAN,TON BLOCKCHAIN]
---

## Overview of the Attack 🚨

In this blog entry, TrendAI Research examines a wave of phishing emails observed in May 2026 that targeted Japanese accommodation facilities using Booking.com. This report details the victims, attack techniques used, and characteristics of the malware involved.

### Attack Details 🛡️

In late May 2026, suspicious emails were identified being sent to Japanese partner companies of Booking.com, with the subject line **"Important: Guest Stay Review Request"** (重要：ゲスト滞在レビュー依頼). The attack initiated when a zip file was downloaded by accessing a hyperlink to a suspicious website. The infection began when the user clicked a shortcut link file (LNK) disguised as a photo file within the zip archive.

Unlike conventional phishing campaigns, the malware abuses The Open Network (TON) blockchain platform as a dead drop resolver. This technique allows attackers to update their command-and-control (C&C) server destination without hardcoding it into the malware, making detection and takedown significantly more difficult.

### Impact and Persistence 🔍

TrendAI telemetry confirmed that accesses from the Japan region were the most prevalent. Endpoints infected with the malware, identified as **TrojanSpy.JS.TONRESOLVER.A**, remain in a persistent Keepalive loop awaiting attacker commands. The risk of credential theft and additional malware deployment continues as long as the infection is active.

### Subject Lines and Techniques 📧

The observed attacks targeting Japan included subject lines such as:
- **"重要：ゲスト滞在レビュー依頼 (Important: Guest Stay Review Request)"**
- **"【重要】お客様からの重大な苦情に関するご連絡 (Important: Notification Regarding a Serious Complaint from a Guest)"**

Hyperlink text strings identified were:
- **"Download Photos and Videos"**
- **"証拠写真・動画を確認する (View Evidence Photos and Videos)"**

Additionally, a **"conversational attack"** method was observed. In this approach, the attacker first sent a normal inquiry email without a URL to the accommodation facility's contact person. After receiving a reply, they sent a follow-up email containing a hyperlink with a malicious URL. This technique of gaining the target's trust through initial correspondence is common in advanced persistent threats (APTs).

### Conclusion ⚠️

Caution is warranted as these techniques may be employed in future attacks beyond this investigation. To read the complete article see: [Read full article](https://www.trendmicro.com/en_us/research/26/f/tonresolver.html)