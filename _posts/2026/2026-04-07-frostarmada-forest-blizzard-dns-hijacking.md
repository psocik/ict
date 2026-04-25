---
title: Frostarmada Forest Blizzard DNS Hijacking
date: 2026-04-07
categories: [CYBERSECURITY]
tags: [FROSTARMADA,DNS,HIJACKING,CYBERSECURITY,THREATS]
---

## Frostarmada Forest Blizzard DNS Hijacking 🚨

**Black Lotus Labs**, the threat research team at Lumen Technologies, has been tracking a campaign named **"FrostArmada"** associated with the threat actor group **"Forest Blizzard"**. This network was created and exclusively operationalized by the Forest Blizzard threat actor to conduct operations against targeted organizations aligned with their strategic interests.

The Lumen team is actively tracking Forest Blizzard, a highly adaptive and persistent threat actor linked to Russia's GRU Unit 26165. This campaign demonstrated a new tactic: modifying DNS settings on compromised routers to hijack local network traffic and capture authentication credentials. When users requested targeted domains, the actor redirected traffic to an **Attacker-in-the-Middle (AitM)** node, where credentials were harvested and exfiltrated, enabling a nearly invisible attack that required no interaction from the end user.

The earliest activity began in **May 2025**, with limited targeting. However, after the U.K. National Cyber Security Centre (NCSC) published the report **Authentic Antics** on **August 5, 2025**, Lumen detected widespread router exploitation and DNS redirection starting **August 6, 2025**. This indicates that the threat actor quickly adapted their methods. At the peak of activity in **December 2025**, Lumen detected over **18,000 unique IPs** from at least **120 countries** communicating with Forest Blizzard's infrastructure. These operations primarily targeted government agencies, including ministries of foreign affairs, law enforcement, and third-party email providers.

Lumen Technologies, in collaboration with Microsoft, the FBI, the DOJ, and international partners, disrupted the infrastructure and took it offline.

One of Forest Blizzard's primary activities is email collection, particularly targeting organizations in the logistics, defense, and government sectors. They reverted to an established technique that exploits a fundamental internet technology: **DNS**. By implementing DNS hijacking at a highly localized level, they managed to avoid detection while still fulfilling their objectives.

During our investigation, we discovered two distinct activity clusters associated with the campaign. The first cluster, referred to as the **"expansion team"**, focused on exploiting new devices and bringing them under the control of the threat actor by targeting a large pool of networking equipment via common web interface ports. We suspect the actor attempted to exploit **CVEs** associated with vulnerabilities in the web interface on **TP-Link** and **MikroTik** routers. As the targeted routers were infected by the expansion team, their DNS settings were modified to communicate with actor-controlled **VPS nodes** acting as DNS resolvers.

One of the most concerning techniques associated with this campaign was the harvesting of **OAuth tokens** from workstations on the adjacent LAN of a compromised router. These authentication tokens were obtained through DNS hijacking coupled with an Attacker-in-the-Middle capability. The threat actors exploited the router to gain remote administrative access and modified the default DNS settings on the router to point towards an actor-controlled **Virtual Private Server (VPS)**. DNS changes were then propagated to the workstations on the adjacent LAN via **Dynamic Host Configuration Protocol (DHCP)**.

The actor operated a DNS server to behave like a typical recursive resolver, but when a targeted Fully Qualified Domain Name (FQDN) was queried, it was configured to provide a record back containing its own IP address instead of the correct address. Lumen identified the first AitM node at the IP address **64.120.31[.]96** in May 2025. Lumen then observed a second AitM node at the IP address **79.141.160[.]78**, which became significantly more active on **August 6, 2025**. This was the day after the UK NCSC released its report documenting a new malware family dubbed **Authentic Antics**, which describes a Forest Blizzard-associated malware tool designed to intercept and exfiltrate Microsoft Office account credentials and tokens.

[Read full article](https://www.lumen.com/blog-and-news/en-us/frostarmada-forest-blizzard-dns-hijacking)