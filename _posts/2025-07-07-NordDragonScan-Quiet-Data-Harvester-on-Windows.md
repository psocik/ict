---
title: NordDragonScan Quiet Data-Harvester on Windows
date: 2025-07-07
categories: [MALWARE]
tags: [WINDOWS,DATA-HARVESTER,NORDDRAGONSCAN,CYBERSECURITY]
---

Affected Platforms: Microsoft Windows  
Impacted Users: Microsoft Windows  
Impact: The stolen information can be used for future attacks  
Severity Level: High  

FortiGuard Labs recently uncovered an active delivery site that hosts a weaponized HTA script and silently drops the infostealer “NordDragonScan” into victims’ environments. Once installed, NordDragonScan examines the host and copies documents, harvests entire Chrome and Firefox profiles, and takes screenshots. The package is then sent over TLS to its command-and-control server, “kpuszkiev.com,” which also serves as a heartbeat server to confirm the victim is still online and to request additional data when needed.  

To read the complete article see:  
https://www.fortinet.com/blog/threat-research/norddragonscan-quiet-data-harvester-on-windows.