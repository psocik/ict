---
title: Just 21 IP Addresses Are Now Behind Nearly Half of All RDP Scanning on the Internet
date: 2026-04-10
categories: [CYBERSECURITY]
tags: [RDP,IP ADDRESSES,SCANNING,CYBERSECURITY]
---

## Overview

A fleet of **21 IP addresses** is now generating nearly half of all the **RDP scanning traffic** on the public internet. On **April 7, 2026**, those IPs produced **1,856,167** of the **2,753,274 RDP Crawler sessions** observed globally by the **GreyNoise Observation Grid (GOG)** — **67.4%** of the worldwide total. Across a **48-hour window** from **April 5–7**, the same fleet accounted for **49.7%** of global RDP Crawler activity. 🚀

The **21 RDP fleet IPs** are part of a larger cluster of active addresses in a single autonomous system: **AS213438**, registered in **RIPE WHOIS** to **ColocaTel Inc.** of **Mahe, Seychelles**. GreyNoise does not attribute this activity to a named actor, as IP geolocation describes where infrastructure is routed, not where operators sit.

## Notable Patterns

This is the same ASN GreyNoise previously reported on for producing roughly **10.7 million sessions** the week of **March 5–11, 2026** — before activity collapsed **97.7%** overnight on **March 7** and went quiet for most of the month. In the first week of April, the ASN came back: smaller fleet, tighter geography, single-protocol focus on RDP. Total AS213438 volume scaled roughly **11x** in **24 hours** — from **180,293 sessions** on **April 6** to **2,011,365 sessions** on **April 7**. Then, just as before, it crashed — dropping **99.9%** in a single day and going fully silent by **April 9**. RDP Crawler sessions from AS213438 fell from **1,856,167** on **April 7** to **1,795** on **April 8** to **zero** on **April 9**. 

Two burst-and-crash cycles from the same ASN, same IPs, same pattern, **30 days apart**. 

## Implications

Two things make this notable. First, **21 IPs generating half** of a global scanning category is not normal — typical source distributions are spread across thousands of IPs and hundreds of networks. Country-level or broad reputation feeds tuned to the old distribution are now pointing at the wrong place. Second, the same ASN was recently the loudest thing on the GOG, then fell silent, then came back smaller and narrower — and then crashed again. 

The **Netherlands' global share** jumped from **7.17%** to **53.86%**, while **Romania's share** fell from **29.89%** to **15.78%** — not because Romania dropped, but because the Netherlands grew ~**15x** and changed the denominator. AS213438 accounts for the majority of that country-level shift.

## Conclusion

Inside the fleet, all **21 RDP fleet IPs** are geolocated to the **Netherlands** and span four **/24 network blocks**. The **Amsterdam-and-Lelystad concentration**, on infrastructure routed through a single ASN registered to one trading name, looks like hosting concentration — not a distributed botnet built from compromised devices. This is reinforced by shared protocol fingerprints observed across multiple higher-volume IPs in the fleet, consistent with centralized tool deployment. The fleet targets RDP on **3389** plus alternates **3390, 3391, 3392**, and **PostgreSQL** on **5432** plus **5430, 5431, 5433, 5434, 15432, 25432, 30432, 35432, and 55432**. The same alternate ports appearing across multiple IPs is consistent with a coordinated scanning configuration drawing from a shared target list.

[Read full article](https://www.greynoise.io/blog/ip-addresses-behind-nearly-half-rdp-internet-scanning)