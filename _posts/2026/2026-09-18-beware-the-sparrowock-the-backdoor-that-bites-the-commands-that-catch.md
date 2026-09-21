---
title: Beware the SparroWock The Backdoor That Bites, The Commands That Catch
date: 2026-09-18
categories: [CYBERSECURITY]
tags: [SPARROWOCK,BACKDOOR,CYBERSECURITY,FAMOUSPARROW,MALWARE]
---

## Beware the SparroWock: The Backdoor That Bites, The Commands That Catch

ESET Research's ongoing monitoring of FamousSparrow has borne fruit once again. Our previous public report on FamousSparrow revealed that this China-aligned APT group had developed two new versions of its custom backdoor named SparrowDoor. This time, we discovered that FamousSparrow has switched to a new backdoor, **SparroWocky**, and has been deploying it to several countries in Latin America since at least August 2025.

In what was probably China's reaction to the US showing increased interest in Latin America, FamousSparrow increased its targeting of the region to almost exclusively targeting it in July 2025. A month later, we noticed that the group had started using the new SparroWocky backdoor, which then quickly replaced SparrowDoor as FamousSparrow's main implant. FamousSparrow is extensively targeting governmental organizations in Latin America.

SparroWocky is a modular, C++ backdoor. Its architecture and the techniques used by its authors indicate strong knowledge of anti-analysis tricks and Windows internals. With the switch to SparroWocky, FamousSparrow started to incorporate code from open-source projects directly into its malware. SparroWocky is a full-featured backdoor that manipulates low-level structures in memory and patches code at runtime in order to avoid detection. Additionally, SparroWocky has the capability to load and execute Beacon Object Files, a special type of executable file supported by many red-teaming and penetration-testing tools.

FamousSparrow is a China-aligned cyberespionage group believed to have been active since at least 2019. We first publicly documented the group in a blog post from September 2021 when we observed it exploiting the ProxyLogon vulnerability. The group was initially known for targeting hotels around the world but has also targeted governments, international organizations, trade groups, engineering companies, and law firms. FamousSparrow is the only known user of the SparrowDoor backdoor. As mentioned by Trend Micro, FamousSparrow is linked to Earth Estries; however, the exact nature of the link is not fully known. FamousSparrow has also been publicly linked to Salt Typhoon, but, due to the absence of any technical indicators, we track them as separate.

For more details, check out the full article here: [Read full article](https://www.welivesecurity.com/en/eset-research/beware-sparrowock-backdoor-bites-commands-catch/) 
