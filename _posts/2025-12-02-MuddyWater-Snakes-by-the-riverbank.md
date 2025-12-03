---
title: MuddyWater Snakes by the riverbank
date: 2025-12-02
categories: [CYBERSECURITY]
tags: [MUDDYWATER,ESET,MALWARE,CYBERESPIONAGE]
---

ESET researchers have identified new MuddyWater activity primarily targeting organizations in Israel, with one confirmed target in Egypt. MuddyWater, also referred to as Mango Sandstorm or TA450, is an Iran-aligned cyberespionage group known for its persistent targeting of government and critical infrastructure sectors, often leveraging custom malware and publicly available tools. In this campaign, the attackers deployed a set of previously undocumented, custom tools with the objective of improving defense evasion and persistence. Among these tools is a custom Fooder loader designed to execute MuddyViper, a C/C++ backdoor. Several versions of Fooder masquerade as the classic Snake game, and its internal logic includes a custom delay function inspired by the game’s mechanics, combined with frequent use of Sleep API calls.

- MuddyWater developers adopted CNG, the next-generation Windows cryptographic API, which is unique for Iran-aligned groups and somewhat atypical across the broader threat landscape.
- The group also used more advanced techniques to deploy MuddyViper, a new backdoor, by using a loader (Fooder) that reflectively loads it into memory and executes it.
- We provide technical analyses of the tools used in this campaign, including MuddyViper, the Fooder loader, the CE-Notes browser-data stealer, the LP-Notes credential stealer, the Blub browser-data stealer, and go‑socks5 reverse tunnels.
- During this campaign, the operators deliberately avoided hands-on-keyboard interactive sessions, which is a historically noisy technique often characterized by mistyped commands.

To read the complete article see:  [ESET Blog](https://www.welivesecurity.com/en/eset-research/muddywater-snakes-riverbank/) 
