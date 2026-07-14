---
title: Open Directory Exposes Three Evilginx Phishing Operators
date: 2026-07-13
categories: [CYBERSECURITY]
tags: [EVILGINX,PHISHING,CYBERSECURITY,LEXFO]
---

## Open Directory Exposes Three Evilginx Phishing Operators

A single misconfigured server has exposed the complete toolkit of an active three-actor phishing ecosystem. According to new research from French security firm Lexfo, the open directory was a Python HTTP server left running on a Budapest virtual private server in late April, with directory listing switched on. Phishing configurations, credential logs, remote management installers, and the operator's own Telegram session files were all readable. Behind it was a threat actor tracked as **codemado**, running an Evilginx-based adversary-in-the-middle (AiTM) platform against corporate Microsoft 365 accounts. 🚨

Artefacts on the server tied codemado to an Egyptian operator active on hacking forums since 2018. Beyond the phishing proxy, the host held a seven-tool remote monitoring and management (RMM) arsenal for persistence, including **ScreenConnect** and **SimpleHelp**, plus a custom bulk-mailer of his own build, **MaDoO Blaster**. The other two actors surfaced through the Evilginx forks codemado had cloned. Their link is technical rather than operational: the repositories were public on GitHub, so Lexfo said shared code does not prove coordination.

An operator called **mail-argenta** was traced through infostealer logs carrying his own reused credentials, notably a MySQL password hardcoded into a phishing panel, pointing to a Nigerian individual. A third, **saroula01**, built a framework abusing the OAuth Device Code Flow, a legitimate Microsoft feature the victim completes on a real Microsoft page while the attacker's backend claims the token. Of the three, saroula01's operation was the largest. Lexfo reconstructed a deleted configuration file from git history, and internal bot timestamps dated the campaign to June 2025, meaning it had run for more than a year without apparent interruption. Over that window, it accumulated **218 confirmed victims** across 12 countries, roughly 94% of them corporate, with captured tokens set to refresh automatically in the background. Recovered entries had been silently refreshed up to 25 times, maintaining access long after the initial phish.

A thread running through all three operators is the use of **generative AI** to build the tooling, evidenced by AI co-author metadata on saroula01's commits and a saved development session in mail-argenta's repository. Lexfo also connected codemado's MaDoO Blaster to **The Quarry**, a phishing-as-a-service (PaaS) ecosystem documented by SOCRadar in June and run by an actor known as **RockyBelling**, who promoted the tool to his customers. 🔍

[Read full article](https://www.infosecurity-magazine.com/news/open-directory-exposes-evilginx/)