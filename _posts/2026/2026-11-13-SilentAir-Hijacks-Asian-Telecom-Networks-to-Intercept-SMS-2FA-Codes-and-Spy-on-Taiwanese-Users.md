---
title: SilentAir Hijacks Asian Telecom Networks to Intercept SMS 2FA Codes and Spy on Taiwanese Users
date: 2026-11-13
categories: [CYBERSECURITY]
tags: [SILENTAIR,TELECOM,CYBERSECURITY,TAIWAN,2FA]
---

## SilentAir Hijacks Asian Telecom Networks 🚨

A newly identified spying group, **SilentAir**, has been using hacked equipment within Asian mobile operators to intercept calls and texts of selected individuals, primarily in **Taiwan**. Enea, a telecom and cybersecurity software company based in Stockholm, discovered the group's attack sources in at least six Asian countries and reported its findings this week. While Enea assesses with high confidence that SilentAir is a state-level actor, it has only low confidence in linking its activities to **China**. The company has informed the operators about the locations of SilentAir's sources and noted that the group has been disrupted for now, although it could potentially return.

Mobile operators utilize the **SS7** and **Diameter** protocols to exchange signaling messages that route calls and texts and enable roaming. SilentAir executed its attacks by sending an **UpdateLocation** message, or its Diameter equivalent, to the target's home network. If the home network accepted this message, calls and texts for that individual would be diverted to the attackers. Enea observed that interception made up **18.3%** of the attacks attributed to SilentAir, with some targets being political and government VIPs in their respective countries.

Outside of Taiwan, targets were primarily located in other Southeast and East Asian networks, and occasionally in regions such as **East Africa**, **Central Asia**, the **Middle East**, and **Europe**.

SilentAir also sent silent SMS messages on a large scale, mainly to subscribers in Taiwan. These texts do not display or alert the recipient's phone, and their primary use appears to be checking whether a diversion has been successful. Most silent SMS messages were sent at night, predominantly to individuals in Taiwan. The purpose of these messages remains unconfirmed.

Enea has identified a low-confidence link to **Liminal Panda**, a group involved in earlier telecom intrusions, but does not currently tie the two groups together. In several compromised operators, SilentAir attacks coincided with known Liminal Panda infections. SilentAir's behavior also partially aligns with that of **SCTPE**, a little-known Linux trojan designed to handle SS7 and Diameter traffic. Singapore's Infocomm Media Development Authority (IMDA) has described this tool in a government advisory, referring to it as **SIGweaver**. The agency noted that **CrowdStrike** identified it on January 21 and linked it to Liminal Panda with moderate confidence. However, Enea stated that SilentAir was capable of responding to messages it had not sent itself, a feature that the known SCTPE program lacks. Additionally, SilentAir's operational security appears to be significantly better than that of Liminal Panda.

Enea recommends that operators deploy **GTP-C** and **GTP-U** firewalls and configure them to share information with their SS7 and Diameter firewalls. Operators should also exceed the industry's basic recommendations for signaling security, treat the entire **IPX** as untrusted, enhance detection for signaling protocols within their networks, and integrate signaling security with their overall IT security.

[Read full article](https://thehackernews.com/2026/11/silentair-hijacks-asian-telecom.html)