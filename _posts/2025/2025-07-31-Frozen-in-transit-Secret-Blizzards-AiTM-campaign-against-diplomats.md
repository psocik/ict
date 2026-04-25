---
title: Frozen in transit Secret Blizzard’s AiTM campaign against diplomats
date: 2025-07-31
categories: [CYBERSECURITY]
tags: [CYBERESPIONAGE,MALWARE,DIPLOMATS,SECRET BLIZZARD]
---

Microsoft Threat Intelligence has uncovered a cyberespionage campaign by the Russian state actor we track as Secret Blizzard that has been targeting embassies located in Moscow using an adversary-in-the-middle (AiTM) position to deploy their custom ApolloShadow malware. ApolloShadow has the capability to install a trusted root certificate to trick devices into trusting malicious actor-controlled sites, enabling Secret Blizzard to maintain persistence on diplomatic devices, likely for intelligence collection. This campaign, which has been ongoing since at least 2024, poses a high risk to foreign embassies, diplomatic entities, and other sensitive organizations operating in Moscow, particularly to those entities who rely on local internet providers.

While we previously assessed with low confidence that the actor conducts cyberespionage activities within Russian borders against foreign and domestic entities, this is the first time we can confirm that they have the capability to do so at the Internet Service Provider (ISP) level. This means that diplomatic personnel using local ISP or telecommunications services in Russia are highly likely targets of Secret Blizzard’s AiTM position within those services. In our previous blog, we reported the actor likely leverages Russia’s domestic intercept systems such as the System for Operative Investigative Activities (SORM), which we assess may be integral in facilitating the actor’s current AiTM activity, judging from the large-scale nature of these operations.

To read the complete article see: [Microsoft Blog](https://www.microsoft.com/en-us/security/blog/2025/07/31/frozen-in-transit-secret-blizzards-aitm-campaign-against-diplomats/) 