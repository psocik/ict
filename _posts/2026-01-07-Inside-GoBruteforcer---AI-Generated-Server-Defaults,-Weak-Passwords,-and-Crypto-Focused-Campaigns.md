---
title: Inside GoBruteforcer - AI-Generated Server Defaults, Weak Passwords, and Crypto-Focused Campaigns
date: 2026-01-07
categories: [MALWARE]
tags: [GOBRUTEFORCER,BOTNET,CYBERSECURITY]
---

GoBruteforcer (also called GoBrut) is a modular botnet, written in Go, that brute-forces user passwords for services such as FTP, MySQL, PostgreSQL, and phpMyAdmin on Linux servers. The botnet spreads through a chain of web shell, downloader, IRC bot, and bruteforcer modules. The current wave of campaigns is driven by two factors: the mass reuse of AI-generated server deployment examples that propagate common usernames and weak defaults, and the persistence of legacy web stacks such as XAMPP that expose FTP and admin interfaces with minimal hardening.

According to our estimate, more than 50,000 Internet-facing servers may be vulnerable to GoBruteforcer attacks.

GoBruteforcer is a botnet that turns compromised Linux servers into scanning and password brute-force nodes. It targets internet-exposed services such as phpMyAdmin web panels, MySQL and PostgreSQL databases, and FTP servers. Newly discovered weak credentials are used to steal data, create backdoor accounts, sell access, and expand the botnet. The malicious toolkit is usually split into two parts. The first is an IRC bot that enables remote control of the compromised host, including command execution and updates. The second is a bruteforcer that is fetched later and used to scan random public IP ranges and attempt logins using credentials that are hardcoded or provided by the command and control (C2) server.

The botnet was first described publicly in 2023. In mid-2025, a more sophisticated GoBruteforcer variant was observed in the wild. This new variant introduces a heavily obfuscated IRC bot (rewritten entirely in Go), improved persistence mechanisms, process-masking tricks, and server dynamic credential lists.

Check Point Research (CPR) observed a GoBruteforcer campaign targeting databases of crypto and blockchain projects. On one compromised host, CPR recovered Go-based tools, a TRON balance scanner and TRON and BSC “token-sweep” utilities, together with a file containing approximately 23,000 TRON addresses. On-chain transaction analysis involving the botnet operators’ recipient wallets shows that at least some of these financially motivated attacks were successful. Millions of database and file-transfer servers are publicly reachable on their default ports. Recent data from Shodan (a search engine for internet-connected devices and services) show roughly 5.7 million FTP servers, 2.23 million MySQL servers, and about 560 thousand PostgreSQL servers are exposed to the Internet.

For the complete article, visit [Check Point Research](https://research.checkpoint.com/2026/inside-gobruteforcer-ai-generated-server-defaults-weak-passwords-and-crypto-focused-campaigns/).