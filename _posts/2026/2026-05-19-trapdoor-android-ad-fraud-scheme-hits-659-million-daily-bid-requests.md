---
title: Trapdoor Android Ad Fraud Scheme Hits 659 Million Daily Bid Requests
date: 2026-05-19
categories: [CYBERSECURITY]
tags: [ANDROID,AD-FRAUD,MALVERTISING,CYBERSECURITY]
---

## Trapdoor Android Ad Fraud Scheme Hits 659 Million Daily Bid Requests 🚨

Cybersecurity researchers have disclosed details of a new ad fraud and malvertising operation dubbed **Trapdoor** targeting Android device users. The activity, per HUMAN's Satori Threat Intelligence and Research Team, encompassed **455 malicious Android apps** and **183 threat actor-owned command-and-control (C2) domains**, turning the infrastructure into a pipeline for multi-stage fraud.

"Users unwittingly download a threat actor-owned app, often a utility-style app like a PDF viewer or device cleanup tool," researchers Louisa Abel, Ryan Joye, João Marques, João Santos, and Adam Sell detailed in a report shared with The Hacker News. **These apps trigger malvertising campaigns** that coerce users into downloading additional threat actor-owned apps. The secondary apps launch hidden WebViews, load threat actor-owned HTML5 domains, and request ads. The campaign is self-sustaining in that an organic app install turns into an illicit revenue generation cycle that can be used to fund follow-on malvertising campaigns. One notable aspect of the activity is the use of HTML5-based cashout sites, a pattern observed in prior threat clusters tracked as **SlopAds, Low5, and BADBOX 2.0**.

At the peak of the operation, Trapdoor accounted for **659 million bid requests a day**, with Android apps linked to the scheme downloaded more than **24 million times**. Traffic associated with the campaign primarily originated from the U.S., which took up more than three-fourths of the traffic volume. According to HUMAN, "The threat actors behind Trapdoor also abuse install attribution tools (technology designed to help legitimate marketers track how users discover apps) to enable malicious behavior only in users acquired through threat actor-run ad campaigns, while suppressing it for organic downloads of the associated apps."

Only the second-stage app is used to trigger fraud. Once the organically downloaded app is launched, it serves fake pop-up alerts that mimic app update messages to trick users into installing the next-stage app. This behavior indicates that the payload is activated only for those who fall victim to the advertising campaign. Besides this selective activation technique, Trapdoor employs various anti-analysis and obfuscation techniques to sidestep detection. **"This operation uses real, everyday software and multiple obfuscation and anti-analysis techniques - such as impersonating legitimate SDKs to blend in - to help fuse malvertising distribution, hidden ad fraud monetization, and multi-stage malware distribution,"** Lindsay Kaye, vice president of threat intelligence at HUMAN, said.

Following responsible disclosure, Google has taken steps to remove all identified malicious apps from the Google Play Store, effectively neutralizing the operation. **"Trapdoor shows how determined fraudsters turn everyday app installs into a self-funding pipeline for malvertising and ad fraud,"** Gavin Reid, chief information security officer at HUMAN, said. **"This is another instance of threat actors co-opting legitimate tools - such as attribution software - to aid in their fraud campaigns and help them evade detection."**

[Read full article](https://thehackernews.com/2026/05/trapdoor-android-ad-fraud-scheme-hit.html)