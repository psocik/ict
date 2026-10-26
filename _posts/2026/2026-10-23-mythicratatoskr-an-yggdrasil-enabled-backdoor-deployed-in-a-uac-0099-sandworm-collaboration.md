---
title: MythicRatatoskr An Yggdrasil-enabled Backdoor Deployed in a UAC-0099-Sandworm Collaboration
date: 2026-10-23
categories: [CYBERSECURITY]
tags: [MYTHICRATATOSKR,YGGDRASIL,BACKDOOR,CYBERSECURITY,SANDWORM]
---

## MythicRatatoskr: An Yggdrasil-enabled Backdoor Deployed in a UAC-0099-Sandworm Collaboration

A recent report details activity involving UAC‑0099, which gained initial access on **July 16th, 2025**. This access was subsequently handed off to Sandworm, leading to a data-wiping attack conducted on **September 17th, 2025**. The analysis particularly focuses on the MythicRatatoskr backdoor, which is unique in its use of the Yggdrasil mesh network to communicate with a C&C server hosted within it.

On **July 16th, 2025**, UAC-0099 gained initial access to a grain logistics company in Ukraine via a spearphishing email with a malicious attachment, leading to the execution chain of the MATCHWOK backdoor. One day later, the attackers deployed MythicRatatoskr, a previously undocumented backdoor that communicates with a C&C server hosted inside the Yggdrasil mesh network. We have not seen the backdoor used anywhere else, and we found indications that a Linux variant may also exist.

Yggdrasil is a decentralized mesh network that implements an experimental routing scheme in which the IPv6 communication between the nodes is end-to-end protected. The MythicRatatoskr backdoor uniquely communicates with a C&C server hosted inside this Yggdrasil mesh network. Ultimately, UAC-0099 handed off access to Sandworm, which then carried out a data-wiping attack. Researchers presented these findings about MythicRatatoskr at LABScon on **September 18th, 2026**, and at the Virus Bulletin conference on **October 16th, 2026**.

The handover documented in this report is not an isolated phenomenon. As noted above, Sandworm is attributed to GRU Unit 74455, and UAC-0099's targeting leads us to assess that it is aligned with Russian interests. Earlier in 2025, we uncovered that Russia-aligned Gamaredon collaborated with Turla, another Russia-aligned threat actor; we documented our findings in our blog post Gamaredon X Turla collab. Both groups are linked to the Federal Security Service of the Russian Federation (FSB). This kind of cooperation underscores the potential for coordinated cyberespionage campaigns among Russia-aligned groups, likely intended to amplify their operational impact. 🚀

[Read full article](https://www.welivesecurity.com/en/eset-research/mythicratatoskr-yggdrasil-enabled-backdoor-deployed-uac0099-sandworm-collaboration/)\n