---
title: AsyncRAT Family Threat Overview
date: 2026-06-26
categories: [CYBERSECURITY]
tags: [ASYNCRAT,MALWARE,CYBERSECURITY,THREATS]
---

## AsyncRAT Family Threat Overview

AsyncRAT is a family of open-source Windows remote access trojans (RATs) that has been forked into numerous descendant malware families. Its most prolific descendant, DCRAT (also known as DarkCrystal RAT), has spawned a second generation of forks. Censys searches on **June 16, 2026** confirmed live command-and-control (C2) infrastructure for more than a dozen variants, eight of which are now tracked under their own identifiers (THREAT-245 through THREAT-252).

These forks share more than just code; each new fork tends to inherit the parent's TLS certificate structure, which is a central weakness for defenders. The certificate pattern `O=< Name> By < author>, L=SH, C=CN` is a strong signal for identifying this malware across forks, regardless of which variant is deployed.

### Evolution of the Family

AsyncRAT was first published on GitHub in **January 2019** by a developer using the handle NYAN-x-CAT, building on the groundwork of Quasar RAT (THREAT-0164). AsyncRAT sits at the root, with DCRAT as its most prolific descendant. DCRAT has produced VenomRAT, which in turn has its own cluster of forks including LMTeamRAT and Alfa Red Fox. Other DCRAT children include EchoRAT, Gh0stRAT, BitRAT, CyberSpike, Dumpling RAT, and DarkRAT. The full tree spans roughly **40 named variants** across three tiers of descent.

### Current Status

Censys host-index searches on **June 16, 2026** confirmed live C2 for the high-volume variants, with AsyncRAT having roughly **49 confirmed hosts**, DCRAT with roughly **36 hosts**, Gh0stRAT with roughly **21 hosts**, and VenomRAT with roughly **18 hosts**. Any certificate combining `L=SH, C=CN` with an `O=* By *` organization field, served on a non-standard port, is a strong indicator for the family, regardless of which fork generated it.

### Future Outlook

The family will continue to fork, and new variants will likely keep inheriting the DCRAT certificate structure. A lineage-wide certificate signature should hold up better over time than per-variant name searches. Several named variants currently show no live infrastructure; they may deploy later, which is why the investigation re-runs these searches periodically.

To read the complete article see:
[Read full article](https://censys.com/blog/asyncrat-family-threat-overview/)