---
title: Inside Gamaredon Cyber Operations FSB's Matryoshka #1/3
date: 2026-06-01
categories: [CYBERSECURITY]
tags: [GAMAREDON,CYBERSECURITY,MALWARE,ESPIONAGE]
---

## Inside Gamaredon Cyber Operations: FSB's Matryoshka #1/3

Sekoia.io's Threat Detection & Research (TDR) team closely monitors the activities of Russian Advanced Persistent Threats (APT). In late December 2025, we deployed an opportunistic YARA rule designed to uncover novel initial access vectors. By January 2026, this rule had generated a dozen hits, prompting an in-depth investigation. While we successfully identified the early stages of a Gamaredon infection chain, unknown restrictions prevented us from fully detonating the sequence to observe the final payloads.

To overcome this, we collaborated with a trusted partner who provided over 70 artifacts retrieved directly from compromised hosts. These artifacts not only corroborated the initial attack stages we observed in December but also contained several distinct malware families historically attributed to Gamaredon: a worm, loaders, and a stealer, widely tracked by the community as Pteranodon, GammaLoad, and GammaSteel. By combining our initial findings with the partner-provided artifacts, we reconstructed an important part of Gamaredon's long-term campaign, which is still ongoing at the time of writing. In addition, understanding some stages allowed us to replay live network requests to Gamaredon's Command and Control (C2) servers. This live interaction successfully tricked the staging infrastructure into delivering the most recent versions of the loaders and the final stealer.

This long-term campaign is attributed to Gamaredon (aka ACTINUM, Armageddon, UAC-0010, BlueAlpha), a Russian state-sponsored intrusion set officially linked by national agencies, such as the Security Service of Ukraine (SSU), to the Russian Federal Security Service (FSB). Its targeting remains geographically focused on Ukraine, specifically aiming at government, military, and critical infrastructure entities. Its primary objective is cyberespionage campaigns by establishing persistent access to continuously exfiltrate sensitive documents.

Gamaredon's arsenal has undergone a significant transformation over the last decade, transitioning from Pteranodon custom-built framework into a fragmented and modular malware. Based on our observation, today's Gamaredon capacities are characterized by a proliferation and a highly active development cycle of new malware variants. The TDR team is releasing a series of reports dedicated to dissecting Gamaredon's latest espionage arsenal. This series aims to comprehensively document the full execution chain and the novel methodologies deployed by the group in 2026, contrasting our findings with existing open-source intelligence. Specifically, this first report focuses on the initial access stage and the worm.

[Read full article](https://blog.sekoia.io/fsbs-matryoshka-1-3-gamaredons-gifts-that-keeps-unpacking-gammaphish-and-gammaworm/)