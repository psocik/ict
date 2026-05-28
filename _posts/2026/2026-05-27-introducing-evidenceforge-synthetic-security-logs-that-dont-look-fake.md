---
title: Introducing EvidenceForge - Synthetic Security Logs That Don't Look Fake
date: 2026-05-27
categories: [SECURITY]
tags: [EVIDENCEFORGE,SECURITY,LOGS,CISCO,OPEN-SOURCE]
---

## Introducing EvidenceForge 🚀

A lot of important work in security depends on having realistic log data to work with, and much of that work gets blocked, watered down, or quietly skipped because the data just isn't available. The use cases come up constantly: teaching threat hunters, incident responders, and detection engineers with datasets that have known ground truth; validating that a detection fires on the right activity without drowning in false positives; and training ML models that need labeled, balanced, multi-source telemetry at scale. These are different problems with the same root cause: You need realistic, labeled security logs, and you can't get them easily.

The options for obtaining this data are limited. Real production telemetry is a compliance problem, while public datasets are often so heavily anonymized they no longer resemble the original log sources. What isn't anonymized is stale, narrow, and over-recycled. You can generate data yourself using attack simulation frameworks like Atomic Red Team or MITRE Caldera, but that requires real infrastructure, is time-consuming to operate, and scales poorly when you need variety. Even hiring a red team, which trades complexity for money, still takes weeks and produces only the specific scenario they ran. Synthetic generators, while many existing ones are genuinely useful tools, share a common architectural limitation: They generate events independently, one format at a time, with no shared state across log sources. The result is datasets where events don't tell a coherent story. What analysts detect when they call data synthetic is the absence of a coherent causal story. The logs don't line up because they emit each log entry independently from the others, and they are not modeling a series of connected events.

### EvidenceForge Solution 🌟

EvidenceForge is a new open-source project from Cisco Talos that approaches the problem differently. It features a single canonical event model, causal ordering, realistic background noise, and AI-assisted scenario authoring. The result is a synchronized dataset across 20+ log formats, including Windows, Linux, network, and endpoint detection and response (EDR) telemetry, complete with ground truth documentation and an analyst briefing.

One honest note: No purely synthetic dataset will fool a seasoned analyst in every case, but that's okay. The goal is fidelity that's good enough to be useful, not something that's indistinguishable from production. The core idea is that EvidenceForge inverts the architectural limitation of other generators. Every piece of evidence flows from a single canonical SecurityEvent object. That object carries a timestamp and event type, plus over 30 composable context objects populated as needed: ProcessContext (PID, parent PID, image, command line), NetworkContext (src/dst IP and port, Zeek UID, shared across Zeek, EDR, and SNORT®), AuthContext (username, LogonID, logon type, result), and many more. The consequence of shared contexts is that emitters cannot disagree. There is one PID, one LogonID, one timestamp.

To read the complete article see: [Read full article](https://blog.talosintelligence.com/introducing-evidenceforge-synthetic-security-logs-that-dont-look-as-fake/)