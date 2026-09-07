---
title: Chinese Speaking Threat Actors Targeting Mexican Android Users With Remote Access Trojan
date: 2026-09-04
categories: [CYBERSECURITY]
tags: [MALWARE,PHISHING,ANDROID,REMOTE_ACCESS_TROJAN,CYBERSECURITY]
---

## Chinese Speaking Threat Actors Targeting Mexican Android Users With Remote Access Trojan 🚨

Intel471 Malware Intelligence researchers recently uncovered a sprawling phishing operation that used Meta Ads to distribute a newly identified Android remote access trojan (RAT) targeting Spanish-speaking users in Mexico. This sophisticated spyware, which we are tracking as **PanDa**, provides extensive surveillance to spy on the victim and collect sensitive data, including screen streaming, hidden virtual network computing (HVNC), remote control capabilities, keylogging, screen lock capture, and other actions to control settings of the infected device.

At the heart of this operation is **AppPanda**, a centralized phishing management panel with additional services to drive infections delivered through malicious ads.

We first observed the PanDa-associated phishing campaign in **May 2026**, spreading through Meta Ads with lures for Spanish-speaking users in Mexico to download and install a malicious application masquerading as the Netflix application. The downloaded Android package kit (APK) file, which we track as **ShellA**, serves as a loader for PanDa. In **July**, we observed the actors shift tactics, launching campaigns impersonating NovaFlix and a growing list of fictitious streaming brands to deliver PanDa. By **August**, actors introduced the Facebook Pixel SDK into malvertising campaigns to improve ad-attribution tracking.

During analysis, a tracking request URL led to the discovery of an unauthenticated centralized phishing management panel -- branded **AppPanda** -- which provided a window into the scale of the operation and malvertising campaigns. Over a one-week campaign beginning on **July 2, 2026**, the panel logged more than **350,000 landing page visits**, **200,000 unique visitors**, and nearly **15,000 malicious app downloads** across at least **22 phishing domains** registered. The presence of the Chinese language throughout the panel suggests the phishing infrastructure was developed or maintained by Chinese-speaking threat actors. This as-a-service model lowers the barrier to entry for new affiliates, with services like **APK Factory**, a payload builder supporting PanDa RAT and BTMOB banking trojan, and **BAT1688**, an automated repacking and crypting platform.

Our analysis of the APK file downloaded from the phishing website revealed it was attributed to the Android loader we track as **ShellA**. The actors employed numerous tricks to ensure victims install the PanDa payload, asking users to enable installs outside of the official Google Play store and randomizing part of the APK's signature to defeat simple blocklist/hash-based detection. Once payload installation is complete, the Android RAT executes and requests accessibility services permission, which enables the malicious app to steal secrets the user enters into login pages such as banking apps. Further analysis revealed the malware communicating with the command-and-control (C2) server over a WebSocket connection with no encryption layer. Targeted applications consisted of **62 banks** and financial institutions across Mexico and Nigeria.

The analyzed campaigns demonstrate a highly scalable, cost-effective phishing operation run by Chinese-speaking threat actors. Automated domain registration, landing page customization, and rapid infrastructure deployment allowed the operation to reach substantial scale, with nearly **15,000 malicious APK downloads** in a single week. PanDa's targeting list of **62 banks** and financial institutions, combined with its credential-harvesting capabilities, makes it a direct threat to mobile banking customers.

[Read full article](https://www.intel471.com/blog/chinese-speaking-threat-actors-targeting-mexican-android-users-with-remote-access-trojan)