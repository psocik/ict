---
title: One Target, Two Flags | Rival Espionage Actors Converge On Pakistani Law Enforcement
date: 2026-07-09
categories: [CYBERSECURITY]
tags: [ESPIONAGE,PAKISTAN,CYBERSECURITY,LAW ENFORCEMENT]
---

## One Target, Two Flags: Rival Espionage Actors Converge On Pakistani Law Enforcement

SentinelLABS has been tracking sustained cyberespionage activity against several Pakistani law enforcement organizations, taking place from **February 2024 to April 2026**. All these actors converged on **Balochistan Police** over this period, bringing both a partner and an adversary of Pakistan to the same police force in a province shaped by a separatist insurgency and the regional tensions it has drawn in. 

At Balochistan Police, the compromised assets included servers hosting web applications that manage police and citizen data, such as criminal and biometric records. A suspected **China-nexus** actor planted implants in one of the web applications, weaponizing a tool of Pakistan's police digitalization against its users. 

Suspected China- and India-nexus threat actors carried out intrusions into several Pakistani law enforcement organizations between 2024 and 2026. Our analysis of C2 netflow data revealed that these actors operating **PlugX**, **ShadowPad**, **Cobalt Strike**, and **Remcos** infrastructure have converged on this victim class. 

When multiple cyberespionage actors operate against law enforcement institutions of a single state, the convergence itself is a signal of target value. What draws them is a particular kind of institution: one that holds the government's internal security picture, what it knows about the threats inside its borders, and how it acts against them. The China-nexus activity is most likely motivated primarily by concern for the safety of Chinese nationals. Pakistani law enforcement is a natural collection target for China. The data it holds would let China assess the security environment its nationals face independently, rather than relying on a partner whose protection has repeatedly fallen short. 

For the India-nexus activity, which was focused on Balochistan, the strongest motive is probably the adversarial security relationship between India and Pakistan, in which the province is a recurring flashpoint. Balochistan Police is the same law enforcement institution the China-nexus actors were active against, approached from the opposite direction. 

We observed the highest concentration of intrusions at Balochistan Police. They affected network appliances and web servers hosting several of its web applications, one of which, the **Complaint Management System (CMS)**, drew particular attention. We also identified compromised infrastructure associated with several other Pakistani law enforcement organizations: the **Khyber Pakhtunkhwa Police**, the **Islamabad Police**, and the **Punjab Safe Cities Authority (PSCA)**. 

We group the C2 activity we observed against all these targets into four clusters, each associated with a single malware family or tool: **PlugX**, **ShadowPad**, **Cobalt Strike**, and **Remcos**. PlugX and ShadowPad point to China-nexus cyberespionage groups on the basis of the tooling itself, since both are backdoors shared among multiple such groups. 

We attribute the Remcos C2 server 89.[REDACTED BY DNB EDITORS TO GET PAST GOOGLE FILTERS] to a suspected India-nexus threat actor, which Recorded Future tracks as **TAG-179**. Its infrastructure, tooling, and TTPs overlap to varying degrees with those of the threat actors tracked by Kaspersky as **Mysterious Elephant** and by Qihoo 360 as **APT-C-08 (a.k.a. Bitter)**. Our data shows that TAG-179 has been intensifying its activities and diversifying its TTPs since early 2025. Among the lures is one with direct relevance to Pakistani law enforcement: it displays a decoy document posing as an operational plan for the repatriation of illegal foreigners, including **Afghan Citizen Card (ACC)** holders.

[Read full article](https://www.sentinelone.com/labs/one-target-china-india-espionage-converge-on-pakistani-law-enforcement/)