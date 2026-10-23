---
title: Prince of Persia A Threat Group Hiding in Plain Sight
date: 2026-10-22
categories: [CYBERSECURITY]
tags: [IRAN,CYBER THREAT,MALWARE,APT,ESPIONAGE]
---

## Prince of Persia: A Threat Group Hiding in Plain Sight

For nearly two decades, the Iranian nation-state threat actor **Prince of Persia** has been an active cyber threat, primarily targeting Iranian dissidents and public and private sector organizations in the United States, Europe, and the Middle East. Initially reported in 2016 by Palo Alto Networks' Unit 42, this Advanced Persistent Threat (APT) group covered its tracks and changed strategies in February 2026, following the most recent published research on its activities.

We were able to track and monitor the threat actor's activity, including a shift in its Command and Control (C2) server strategy. Since 2010, this APT group has launched numerous malware attacks: **Operation Mermaid**, **Infy**, **Foudre**, **Tonnerre**, and **Tornado**. Tornado, the newest malware, builds on the older malware codebase and includes new capabilities such as a Telegram-based C2 channel and advanced Domain Generation Algorithms (DGAs).

### Infy: The Espionage Tool

Infy functions as a full-featured espionage tool. Its high-end variant, known as **Infy M**, features a hidden graphical user interface (GUI) control panel and HTTP/FTP capabilities, supporting remote execution commands. After publishing its Infy research in 2016, Unit 42 conducted a takedown operation, which severed the attack group's access to most of its victims. Unit 42 affirmed the group's connection to Iran, as most victims were in the country or were Iranian dissidents, and the group did not seem to be financially motivated.

Subsequent research reaffirmed this connection, noting Prince of Persia compromised two news websites related to Jundallah as early as 2010, exploiting ActiveX vulnerabilities. Prince of Persia's activity around the 2013 Iranian Presidential elections targeted the press, including BBC Persian, civil society members, and activists. After Unit 42's takedown, the Telecommunication Company of Iran blocked and redirected any traffic originating from Iran aimed at Palo Alto's sinkholes, supporting the theory that the group is connected to the Iranian government.

### Recent Developments

In August 2017, Unit 42 observed Prince of Persia activity again through new malware dubbed **Foudre**, a first-stage malware used to map victims' identities, establish persistent access, and perform browser credential theft. In 2018, Foudre version 8 introduced **Tonnerre**, a second-stage malware that provides deep data exfiltration, capturing audio, screenshots, and sensitive documents. More recent iterations use a DGA and integrate Telegram bots and private channels as a fallback mechanism for stealthy C2 purposes. Tonnerre also uses aggressive mechanisms like anti-takeover RSA signatures to prevent cybersecurity researchers from sinkholing its traffic.

In February 2026, SafeBreach discovered **Tornado**, dropped via one-day software vulnerabilities like WinRAR exploits. Tornado uses both HTTPS and the Telegram API as a covert C2 channel and supports blockchain-based exfiltration. It also implements RSA signature validation in Tornado attacks to strictly authenticate incoming C2 requests, locking out security researchers.

Since March 2026, Prince of Persia has gone dark, with no publicly identified activity. However, we were able to track and monitor the group's activity, including a shift in its C2 server strategy: the group abandoned known C2 servers, built a new bank of active C2 servers, changed hosting providers, and shifted from Virtual Private Server (VPS) hosting to public hosting. Our discovery of the Tornado second-stage C2 server reveals that for the first time in a decade, the Iranian threat actor decided to host its new C2 server on US soil -- at the same time as the beginning of the recent hostilities between Iran and the United States.

[Read full article](https://www.semperis.com/blog/prince-of-persia-threat-group-hiding-in-plain-sight/)\n