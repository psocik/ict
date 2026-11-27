---
title: Volant Manticore Flying Under The Radar
date: 2026-11-26
categories: [CYBERSECURITY]
tags: [IRAN,ESPIONAGE,CYPRUS,MALWARE,CYBERSECURITY]
---

## Volant Manticore Flying Under The Radar

**Source:** Checkpoint Research  
**Date Published:** November 26, 2026  

Check Point Research has identified **Volant Manticore**, a previously undocumented Iranian threat group linked to Iran's Ministry of Intelligence and Security (MOIS). This group is notable for designating **Cyprus** as a primary espionage target, focusing on telecommunications companies, airlines, and critical infrastructure. What began in **July 2026** as a single backdoor delivered to a Cyprus-based airline through a fake CV has since expanded into a broader cluster of activity traced back to **September 2025**. Cyprus is at the center of Volant Manticore's operations, given its deepening defensive and energy ties with **Israel** and **Greece**, and its role as a hub for Western military operations in the region, making it a natural target for Iranian intelligence collection. The group's focus on the island's telecommunications companies and airlines aligns with Iran's historical operational activity against individuals in Cyprus.

The group employs **KuboShell**, a new backdoor utilizing **IPFS** for command-and-control (C2) functions, to deploy the **Homa Framework**, a post-compromise framework built on a reimplementation of MuddyWater's **MuddyC2Go** client. Alongside custom malware, Volant Manticore delivers RMM tools and conducts credential-harvesting campaigns. Further analysis has illuminated the operators' internal setup, including development, testing, and operational environments, both on-premise and in the cloud. Observations indicate the group tested their tooling against antivirus products before deployment and utilized **Fortinet SSL VPN clients**, suggesting access to victims' networks via VPN.

While multiple links to MuddyWater have been identified, it is assessed that Volant Manticore likely consists of former MuddyWater operators who branched off and currently operate as a separate threat cluster. MuddyWater, an Iranian espionage group linked to the MOIS, has been active since at least **2017**. Volant Manticore shares tooling and tradecraft with MuddyWater, but their narrow regional focus, custom implants, and distinct TTPs (Tactics, Techniques, and Procedures) differentiate them. The targeting priorities of Volant Manticore appear responsive to regional geopolitical developments. In **September 2026**, coinciding with escalating hostilities between **Saudi Arabia** and the Iranian-backed **Houthis**, Volant Manticore abruptly shifted their attention to Saudi Arabia, targeting healthcare organizations.

For more details, [Read full article](https://research.checkpoint.com/2026/volant-manticore-flying-under-the-radar/).