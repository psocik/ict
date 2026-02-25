---
title: The Shadow Campaigns - Uncovering Global Espionage
date: 2026-02-05
categories: [CYBERSECURITY]
tags: [CYBERESPIONAGE,GLOBAL,UNIT42,TGR-STA-1030]
---

## The Shadow Campaigns - Uncovering Global Espionage 🚀

This investigation unveils a new cyberespionage group that Unit 42 tracks as **TGR-STA-1030**, with activity referred to as the **Shadow Campaigns**. We assess with high confidence that TGR-STA-1030 is a state-aligned group operating out of Asia. Over the past year, this group has compromised government and critical infrastructure organizations across **37 countries**, meaning approximately one out of every five countries has experienced a critical breach from this group. 

Further, between **November and December 2025**, we observed the group conducting active reconnaissance against government infrastructure associated with **155 countries**. This group primarily targets government ministries and departments, successfully compromising five national-level law enforcement/border control entities, three ministries of finance, and various other government ministries and departments globally that align with economic, trade, natural resources, and diplomatic functions.

Unit 42 first identified TGR-STA-1030 (aka UNC6619) upon investigating a cluster of malicious phishing campaigns targeting European governments in early **2025**. We assess with high confidence that TGR-STA-1030 is a state-aligned group that operates out of Asia, based on frequent use of regional tooling and services, language setting preferences, targeting and timing that routinely align with events and intelligence of interest to the region, upstream connections to operational infrastructure originating from the region, and actor activity routinely aligning with **GMT+8**. Additionally, we found that one of the attackers uses the handle **“JackMa.”**

These phishing campaigns followed a pattern of being sent to government email recipients with a lure of a ministry or department reorganization and links to malicious files hosted on **mega.nz**. We assess that an Estonian government entity identified the campaign and uploaded one such ZIP archive to a public malware repository.

Analyzing the archive, we found that the contents were last modified on **Feb. 14, 2025**, and contained an executable file with an identical name as the ZIP, originally named **DiaoYu.exe**. The term Diaoyu translates to fishing, or phishing in a cybersecurity context. The malware employs a dual-stage execution guardrail, requiring a horizontal screen resolution greater than or equal to **1440** and performing an environmental dependency check for a specific file (**pic1.png**) in its execution directory. If these prerequisites are not met, the process terminates gracefully. The malware also audits the host for specific cybersecurity products, before ultimately installing a **Cobalt Strike** payload.

In addition to phishing campaigns, the group often couples exploitation attempts with their reconnaissance activities to gain initial access to target networks. We have not observed the group developing, testing, or deploying any zero-day exploits, but they are comfortable testing and deploying a wide range of common tools, exploitation kits, and proof-of-concept code for **N-day exploits**, such as **CVE-2019-11580**.

We assess that the group relies heavily on a mix of command-and-control (C2) frameworks and tools common to the actors’ region. From **2024** through early **2025**, we observed the group commonly deploying **Cobalt Strike** payloads, but over time the group slowly transitioned to **VShell** as its tool of choice. VShell is a Go-based C2 framework, often configured with web access on **5-digit ephemeral TCP ports** using ordered numbers. Within the past year, we assess that the group has also leveraged frameworks like **Havoc**, **SparkRat**, and **Sliver** with varying degrees of success. TGR-STA-1030 has frequently deployed web shells on external-facing web servers as well as on internal web servers to maintain access.

[Read full article](https://unit42.paloaltonetworks.com/shadow-campaigns-uncovering-global-espionage/)