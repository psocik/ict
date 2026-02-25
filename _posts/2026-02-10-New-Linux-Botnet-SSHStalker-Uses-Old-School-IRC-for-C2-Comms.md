---
title: New Linux Botnet SSHStalker Uses Old-School IRC for C2 Comms
date: 2026-02-10
categories: [SECURITY]
tags: [LINUX,BOTNET,MALWARE,IRC,C2]
---

## New Linux Botnet SSHStalker Uses Old-School IRC for C2 Comms 🚀

A newly documented Linux botnet named **SSHStalker** is using the **IRC (Internet Relay Chat)** communication protocol for command-and-control (C2) operations. The SSHStalker botnet relies on classic IRC mechanics such as multiple C-based bots and multi-server/channel redundancy instead of modern C2 frameworks, prioritizing resilience, scale, and low cost over stealth and technical novelty. According to researchers at threat intelligence company **Flare**, this approach extends to other characteristics of SSHStalker’s operation, like using noisy SSH scans, one-minute cron jobs, and a large back-catalog of 15-year-old CVEs.

> "What we actually found was a loud, stitched-together botnet kit that mixes old-school IRC control, compiling binaries on hosts, mass SSH compromise, and cron-based persistence. In other words, a scale-first operation that favors reliability over stealth," Flare says.

### Infection and Propagation 🔍

SSHStalker achieves initial access through automated SSH scanning and brute forcing, using a Go binary that masquerades as the popular open-source network discovery utility **nmap**. Compromised hosts are then used to scan for additional SSH targets, resembling a worm-like propagation mechanism for the botnet. Flare found a file with results from nearly **7,000 bot scans**, all from January, focused mostly on cloud hosting providers in **Oracle Cloud infrastructure**.

### Payloads and Persistence 🔄

Once SSHStalker infects a host, it downloads the **GCC tool** for compiling payloads on the victim device. The first payloads are C-based IRC bots with hard-coded C2 servers and channels, enrolling the new victim in the botnet’s IRC infrastructure. The malware fetches archives named **GS** and **bootbou**, which contain bot variants for orchestration and execution sequencing. Persistence is achieved via cron jobs that run every **60 seconds**, invoking a watchdog-style update mechanism that checks whether the main bot process is running and relaunches it if terminated. The botnet also contains exploits for **16 CVEs** targeting Linux kernel versions from the **2009-2010 era**, used to escalate privileges after the earlier brute-forcing step grants access to a low-privileged user.

### Monetization and Recommendations 💰

Regarding monetization, Flare noticed that the botnet performs **AWS key harvesting** and website scanning. It also includes **cryptomining kits** such as the high-performance **Ethereum miner PhoenixMiner**. Distributed denial-of-service (DDoS) capabilities are also present, though the researchers noted they have not yet observed any such attacks. Currently, SSHStalker’s bots just connect to the C2 and then enter an idle state, suggesting testing or access hoarding for now.

Flare has not attributed SSHStalker to a particular threat group, though it noted similarities with the **Outlaw/Maxlas botnet ecosystem** and various Romanian indicators.

### Mitigation Recommendations ⚠️

The threat intelligence company suggests placing monitoring solutions for compiler installation and execution on production servers, and alerts for IRC-style outbound connections. Cron jobs with short execution cycles from unusual paths are also big red flags. Mitigation recommendations include:
- Disabling SSH password authentication
- Removing compilers from production images
- Enforcing egress filtering
- Restricting execution from ‘/dev/shm’

To read the complete article see:
[Read full article](https://www.bleepingcomputer.com/news/security/new-linux-botnet-sshstalker-uses-old-school-irc-for-c2-comms/)