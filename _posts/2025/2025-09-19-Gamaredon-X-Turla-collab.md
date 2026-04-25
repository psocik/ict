---
title: Gamaredon X Turla collab
date: 2025-09-19
categories: [MALWARE]
tags: [GAMAREDON,TURLA,ESET,MALWARE,UKRAINE]
---

In February 2025, via ESET telemetry, we detected four different Gamaredon-Turla co-compromises in Ukraine. On those machines, Gamaredon deployed a wide range of tools, including PteroLNK, PteroStew, PteroOdd, PteroEffigy, and PteroGraphin, while Turla only deployed Kazuar v3.
On one of those machines, we were able to capture a payload showing that Turla is able to issue commands via Gamaredon implants. PteroGraphin was used to restart Kazuar, possibly after Kazuar crashed or was not launched automatically. Thus, PteroGraphin was probably used as a recovery method by Turla. This is the first time that we have been able to link these two groups together via technical indicators (see First chain: Restart of Kazuar v3).

In April and June 2025, we detected Kazuar v2 installers being deployed directly by Gamaredon tools (see Second chain: Deployment of Kazuar v2 via PteroOdd and Third chain: Deployment of Kazuar v2 via PteroPaste). This shows that Turla is actively collaborating with Gamaredon to gain access to specific machines in Ukraine.

To read the complete article see:

[Gamaredon X Turla collab](https://www.welivesecurity.com/en/eset-research/gamaredon-x-turla-collab/) 
