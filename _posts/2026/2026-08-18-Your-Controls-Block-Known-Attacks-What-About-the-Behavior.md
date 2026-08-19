---
title: Your Controls Block Known Attacks. What About the Behavior?
date: 2026-08-18
categories: [SECURITY]
tags: [SECURITY,ATTACKS,BEHAVIOR,PREVENTION,DETECTION]
---

## Overview

Now in its fourth year, the **Blue Report 2026** from Picus Labs measures how enterprise prevention and detection actually perform in production, across more than **338 million attack simulations** run in real customer environments from January through June 2026. The headline is a genuine recovery, with a caveat: yes, prevention effectiveness rose from **62% to 69%**, back to its 2024 peak. But that number is a stack-wide average, and it masks a softer, more vulnerable interior.

The same controls that block a well-known attack tool let a quieter version of the same technique slip straight past your defenses. What decides the outcome isn't the product in place, but how recognizable the attacker's method is, and whether anyone tested for the quiet variant. In this year's data, the **IOC-based prevention rate** for malware downloads fell to **50%** across customer environments, from **60% last year** and **71% in 2024**.

## Key Findings

Whether a defense holds depends on which of two questions you put to it. **IOC-based testing** asks whether a control recognizes known bad, while **behavioral, TTP-based testing** asks whether a control stops the action, by any route. Artifacts are cheap to change; behavior is not.

The report highlights that changing how **Mimikatz** dumps credentials can cause prevention rates to drop dramatically. Dumping credentials from **LSASS process memory**, the classic and heavily signatured path, was blocked in **94% of attempts**. However, pulling **RDP credentials** from other memory locations with the same tool only saw **17% prevention**, and reading **LSA Secrets** from the local registry plummeted to **3%**. All three are siblings under one parent technique, **OS Credential Dumping (T1003)**, and all three end with the attacker holding your precious credential material. The only variable was how conspicuous the route was. Reading LSA Secrets never touches lsass; it runs as SYSTEM and reads a registry hive, indistinguishable from ordinary privileged activity.

Inside the environment, prevention drops to **37%**. While the **69% overall Prevention Rate** measures how well controls stop attacks at the boundary, autonomous penetration testing measures something harder: what an attacker can actually accomplish once they're inside as an "authenticated user." Across the full set of those post-compromise actions, only **37% were blocked**. More specifically, credential material read passively from memory and the registry was prevented in only **22% of cases**, with local registry secret extraction blocked in less than **1%**. Discovery and collection stood at **10%**, with **SharpHound domain enumeration** and local file collection running almost entirely unopposed.

To close the gap, organizations should run both known-bad testing and behavioral validation. Known-bad testing is the baseline for perimeter controls, while behavioral validation belongs to the endpoint and detection layer. Proving credential access is covered means testing every route to it: **LSASS memory**, the registry, alternate memory locations, native tooling, and recompiled builds. The report concludes that none of this calls for a bigger stack; it calls for knowing which controls you already own will break the chain.

[Read full article](https://www.bleepingcomputer.com/news/security/your-controls-block-known-attacks-what-about-the-behavior/)