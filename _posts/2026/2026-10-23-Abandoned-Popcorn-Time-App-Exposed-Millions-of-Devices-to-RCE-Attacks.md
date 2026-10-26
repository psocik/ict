---
title: Abandoned Popcorn Time App Exposed Millions of Devices to RCE Attacks
date: 2026-10-23
categories: [SECURITY]
tags: [POPCORN-TIME,RCE-ATTACKS,VULNERABILITY,CYBERSECURITY,MALWARE]
---

## Abandoned Popcorn Time App Exposed Millions of Devices to RCE Attacks 🚨

Researchers have remotely disabled a vulnerable updater in the abandoned Time4Popcorn app, a fork of the Popcorn Time BitTorrent client. This action closed a security flaw that could have allowed attackers to execute malicious code with elevated privileges on millions of computers. The vulnerability, tracked as **CVE-2026-30612**, affects Windows and macOS updaters that contacted the app's abandoned domain (popcorntimeupd.xyz) over unencrypted HTTP and accepted executables without verifying digital signatures.

### Key Findings 🔍
- Anyone controlling the update domain could manipulate HTTP traffic and execute code as **SYSTEM** on Windows and as **root** on macOS.
- The Popcorn Time app featured a Netflix-style interface that integrated BitTorrent downloads, allowing users to consume illegal content directly within the app.
- Forks such as Time4Popcorn quickly attracted millions of users.

Researchers at **Eye Security** discovered the security risk after registering the popcorntimeupd.xyz domain and observed up to **3 million Windows** and **350,000 macOS** client connections to Time4Popcorn. Connections came from residential ISPs and corporate, government, and military networks. However, none of the users appeared to be actively using the app, suggesting it had been installed and forgotten. 

> "If we were able to send an update, we could potentially get code execution on millions of systems," Eye Security notes, adding that "the impact would be severe if this were to fall into the wrong hands."

Following this discovery, the researchers registered 14 more domains associated with the service.

### Remediation Efforts 🛠️
Between November 2025 and March 2026, Eye used the vulnerable update mechanism to deliver remediation code that stopped and disabled the updater. Their payload collected no host data or telemetry and deleted no files on the users' computers, keeping their actions within a fully legal context. Eye explains that it had to modify its payload during testing to evade antivirus products that flagged it for disabling a service. After deploying the remediation, Eye recorded **2 million update downloads**, and by March 1 this year, requests to its update domain dropped by **98%**. Following the successful completion of the remediation operation, domain ownership was passed to the non-profit security organization **The Shadowserver Foundation**.

### Ongoing Risks ⚠️
Despite this success, the researchers warned that the risk is not fully eliminated for users of the app. First, Android users remain exposed as installing an update would require user interaction, and researchers could not disable the updater remotely for the mobile platform. Second, the Time4Popcorn app uses a severely outdated Chrome engine from 2014, with no sandbox protections, which could be exploited in attacks. The best course of action would be for users to remove the software entirely from their systems.

For more detailed information, you can read the full article here: [Read full article](https://www.bleepingcomputer.com/news/security/abandoned-popcorn-time-app-exposed-millions-of-device-to-rce-attacks/) 
