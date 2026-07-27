---
title: Hotel Wi-Fi Routers Compromised to Steal Corporate Login Credentials
date: 2026-07-24
categories: [CYBERSECURITY]
tags: [HOTEL,WIFI,CYBERSECURITY,CREDENTIALS,DNS]
---

## Hotel Wi-Fi Routers Compromised to Steal Corporate Login Credentials

A widespread DNS poisoning campaign is targeting hotels, conference venues, and the hospitality sector with credential harvesting attacks designed to steal corporate login credentials from visitors, researchers have warned. Identified by cybersecurity analysts at ReliaQuest, the campaign begins by targeting routers used to provide public Wi-Fi to visitors to hotels, conference centers, and other shared venues frequently visited by corporate employees. 🌍

These compromised Wi-Fi gateways were identified around the world, including across multiple US cities, India, and Saudi Arabia. In a blog post published on July 23, ReliaQuest researchers said that they believed initial access to the devices was achieved by exploiting exposed management interfaces, such as SSH, SNMP, and web administration consoles, as well as weak or reused admin login credentials. 🔑

With this access, the attacker modifies the configurations of the compromised routers and uses DNS poisoning to redirect the web traffic, funneling connections for legitimate domains through attacker-controlled infrastructure. This means that a user can be compromised without the need for a phishing link, a malicious attachment, or the attacker touching the device in any way. 😱

With no indication that anything could be amiss, the user will continue to use their device normally, oblivious to how the attackers can now monitor their activity, complete with being provided with the username, password, and other sensitive information which belongs to the victim. By targeting hotels and conference venues known to be used by traveling corporate employees, the attackers can potentially get hold of a wide range of credentials which could be exploited to access sensitive information. 🔍

ReliaQuest researchers warned, "The compromised devices we investigated were appliances primarily used at hotels and other organizations running captive Wi-Fi services." They added, "However, any operator of a captive portal network - such as airports, conference centers, co-working spaces, universities, healthcare facilities, and event venues - faces a structurally similar attack surface." ⚠️

The researchers also noted that the tradecraft used in the DNS poisoning campaign, which is still ongoing, is similar to previous campaigns attributed to APT28, also known as Fancy Bear and Forest Blizzard, a cyber espionage group linked to the Russian military intelligence agency (GRU). ReliaQuest has issued advice on how to prevent DNS poisoning from reaching endpoints, eliminating the attack surface, and detecting credential-harvesting activity if it occurs. The recommendations include: 
- Enforcing always-on VPN with full-tunnel configuration: Require all corporate devices to use a VPN with full-tunnel configuration.

[Read full article](https://www.infosecurity-magazine.com/news/hotel-wifi-dns-poisoning/)