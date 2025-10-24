---
title: Anomali Cyber Watch - Nimbus Manticore, Spoofed IC3 Portals, a Record-Breaking DDoS Attack, and More
date: 2025-10-23
categories: [CYBERSECURITY]
tags: [APT,DDOS,CYBER CRIME,VULNERABILITY]
---

The Iranian APT group Nimbus Manticore is expanding its espionage activities into Western Europe, targeting defense, aerospace, and telecommunications organizations. Researchers have observed the group using tailored spear-phishing campaigns disguised as HR recruiters, directing victims to fake career portal sites. These portals require preassigned, unique credentials, adding a layer of perceived legitimacy.

The malware delivered includes a new backdoor called MiniJunk, an evolution of previous Minibike variants. MiniJunk employs modular side-loading chains, obfuscation, junk code, and signed binaries to avoid detection. A companion stealer, MiniBrowse, is used to target credentials stored in web browsers. The group's infrastructure leverages both Cloudflare and Azure App Services for resilience, and their domains often impersonate major aerospace and defense brands. The job market lure has become a staple across industries.

The FBI is warning of fraudulent websites impersonating the Internet Crime Complaint Center (IC3.gov). These spoofed portals are designed to trick victims into submitting personally identifiable information and financial details. The harvested data can be used for identity theft, financial fraud, or leveraged in further cybercrime schemes. Attackers register domains that differ from the official site by small variations. The authentic IC3 portal is located at ic3.gov only. The IC3 portal is also used by cybersecurity and business professionals to file reports on behalf of their organizations which could include corporate breach details, contact data for security staff, technical indicators, or even financial account information.

Cloudflare recently mitigated a record-breaking Distributed Denial-of-Service (DDoS) attack peaking at 22.2 terabits per second (Tbps) and 10.6 billion packets per second (Bpps). The attack lasted for 40 seconds and targeted a single IP address belonging to a European infrastructure customer. The attack originated from more than 404,000 unique source IPs across 14+ autonomous systems. Analysts point to the Aisuru botnet. The 22.2 Tbps peak eclipsed the previous 11.5 Tbps record.

Cisco has disclosed CVE-2025-20352, a high-severity zero-day vulnerability in IOS and IOS XE software actively exploited in attacks. The flaw is a stack-based buffer overflow in the SNMP subsystem. Attackers with low privileges can trigger denial-of-service, while those with higher privileges can achieve full root access by sending crafted SNMP packets over IPv4/IPv6. Cisco urges immediate upgrades to patched releases. If patching cannot be applied immediately, Cisco advises restricting SNMP access on affected systems to trusted users.

Read the complete article [here](https://www.anomali.com/blog/anomali-cyber-watch-nimbus-manticore-spoofed-ic3-portals-a-record-breaking-ddos-attack-and-more).