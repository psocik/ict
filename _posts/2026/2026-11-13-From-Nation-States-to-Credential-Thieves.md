---
title: From Nation-States to Credential Thieves
date: 2026-11-13
categories: [CYBERSECURITY]
tags: [CREDENTIAL THEFT,MOBILE SECURITY,IOS,ANDROID,CYBER THREATS]
---

## From Nation-States to Credential Thieves

This year, adversaries have put leaked iOS exploit toolkits to work at scale, delivering attacks through online ads and reaching ordinary employees while erasing their traces before defenders could respond. The leaks of **DarkSword** and **Coruna** have placed that capability in the hands of criminal organizations worldwide. Attackers no longer need a government's budget to break into iPhones -- AI-based vulnerability hunting levels the playing field.

In iVerify's detections, the individuals targeted were not executives but rank-and-file employees swept up in broad, untargeted campaigns delivered through websites, ads, and, in at least one case, an App Store app. Android has long faced the same reality, with a steady supply of cheap, ready-made kits that allow criminals to take over phones remotely.

The prevalence of iOS spyware across iVerify's consumer user base is **1.07 infections per 1,000 devices**, or at least **1 in 900**. The rate has barely moved, and we are seeing confirmed attacks weekly, many targeting on-device crypto wallets and delivered via watering hole attacks. **Three in four** of this year's detections were criminal adversaries stealing credentials and cryptocurrency, not state-sponsored actors. Criminal attacks have overtaken the abuse of mercenary spyware (commercial spyware sold to governments) as a primary mobile threat. **75%** of detections were criminal. Furthermore, **100%** of enterprise detections from criminal actors were rank-and-file.

Between raiding iPhone keychain stores, messages, notes files, and crypto wallets, DarkSword and Coruna go way beyond stealing 2FA codes and session tokens, marking this year as the first demonstration of wormable malware that can expand the blast radius even further by automatically spreading to other devices in a victim's contact list. iOS **27.2** contained **163 security fixes**, the most ever. The marked increase in the vulnerabilities fixed in each iOS release demonstrates AI's impact on accelerating how quickly flaws are found. AI is lowering the bar for mobile exploitation. To our knowledge, not one device we detected under DarkSword or Coruna attack received an **Apple Threat Notification (ATN)**, the warning Apple sends to users it believes are being successfully or unsuccessfully targeted. ATNs appear overly focused on nation-state threats like **Pegasus** and **Paragon**, well-known commercial spyware tools. Adversaries now clean up more aggressively, and the traces that remain age off the device faster, effectively making the evidence go dark.

Where DarkSword and Coruna exploit flaws in iOS, every Android RAT we observed gets in by persuasion and navigating victims through the "allow restricted settings" step Android implemented as an extra security layer since version 13. Android-focused threat actors lean on social engineering. According to the report, "In short, mobile exploitation has gone mass-market. Criminals now reach ordinary employees at scale, silently, through ads, the App Store, and cheap kits." The old threat model no longer holds. Victims are overwhelmingly ordinary employees at their desks and in their homes. Corporate access is exposed. Exploits can pull work passwords and sign-in tokens from the iPhone keychain. Containerization won't save an enterprise, as exploits like DarkSword can puncture right through common data governance tools on mobile.

Mobile devices now warrant the same endpoint detection and response coverage as laptops and servers. The findings point to three priorities: keep iOS and Android devices updated, restrict sideloading, and detect attacks while they are running via true mobile EDR, before the evidence ages off.

[Read full article](https://learn.iverify.com/hubfs/AMTR/iVerify-Advanced-Mobile-Threat-Report-2026.pdf)