---
title: CubePilot Drone Software Developer Hit by DNS Hijacking
date: 2026-07-28
categories: [SECURITY]
tags: [CUBEPILOT,DNS,HIJACKING,DRONE,SECURITY]
---

## CubePilot Drone Software Developer Hit by DNS Hijacking 🚨

CubePilot, an Australian firm that designs flight controllers for drones (UAVs), announced a severe operational disruption caused by a DNS hijacking attack. Hijacking domain name system (DNS) records allows threat actors to redirect users to their infrastructure, diverting traffic intended for a legitimate service. This exposes users to dangerous scenarios such as sensitive data interception, malware delivery, and phishing.

According to a status update published on CubePilot's website, an attacker gained control of the cubepilot.org domain DNS settings on July 24, allowing them to intercept traffic intended for internal systems.

The attacker also obtained TLS certificates covering all cubepilot.org subdomains, meaning users visiting affected services would have seen valid HTTPS connections while unknowingly landing on attacker-controlled infrastructure. "The certificates obtained by the attacker covered every cubepilot.org subdomain, so credentials entered on any of our services on July 24 may have been captured -- the portal and the forum included," reads the announcement. "If you used the same password anywhere else, change it there now," warned CubePilot.

CubePilot said it regained control of its domains on July 24, revoked the fraudulently issued certificates, preserved evidence, notified relevant providers, and reported the incident to the Australian Cyber Security Centre and law enforcement. CubePilot designs "autopilots" and navigation hardware for UAVs used in surveying, search and rescue, agriculture, and also defense and government applications. Currently, all OEM services, the community forum, and the documentation portal are offline.

Additionally, CubePilot's CEO, Philip Rowse, stated on LinkedIn that the platform's ERP portal has also been taken offline as a precaution while an investigation into the incident is underway.

Regarding the integrity of the published firmware images, CubePilot is currently evaluating them and advised not to flash images downloaded on July 24-25 until checks to confirm their safety are completed. Firmware obtained before July 24 is currently considered safe to use.

Finally, clients who receive payment requests claiming to be from CubePilot are advised not to take any action and instead to confirm them over the phone with their usual contact.

[Read full article](https://www.bleepingcomputer.com/news/security/cubepilot-drone-software-dev-hit-by-dns-hijacking-to-intercept-traffic/)