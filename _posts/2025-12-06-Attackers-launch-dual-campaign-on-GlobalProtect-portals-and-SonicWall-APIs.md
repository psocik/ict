---
title: Attackers launch dual campaign on GlobalProtect portals and SonicWall APIs
date: 2025-12-06
categories: [SECURITY]
tags: [GLOBALPROTECT,SONICWALL,API,CYBERSECURITY]
---

A campaign began on December 2 targeting Palo Alto GlobalProtect portals with login attempts and scanning SonicWall SonicOS API endpoints. The activity came from over 7,000 IPs tied to German hosting provider 3xK GmbH, which operates its own BGP network (AS200373).

The December traffic reuses three client fingerprints previously seen in a late-September to mid-October wave. That earlier surge came from four typically non-malicious ASNs (NForce Entertainment, Data Campus, Flyservers, and Internet Solutions & Innovations) which generated over 9 million legitimate HTTP sessions, mostly hitting GlobalProtect portals and authentication endpoints. The reappearance of identical fingerprints on new infrastructure signals consistent tooling across seemingly separate events.

GreyNoise also observed that a surge of scans against SonicWall SonicOS API endpoints on 3 December carried the same three client fingerprints previously seen in the 2 December GlobalProtect login spike and in the large September–October brute-forcing campaign. The researchers pointed out that although the infrastructure and targeted vendors are different, the identical fingerprints reveal continuity in the attacker’s tooling. Telemetry shows a clear rhythm: intense login and brute-force activity from clean ASNs between late September and mid-October, a slowdown through late November, then the same client resurfacing on 3xK’s infrastructure on 2 December to probe Palo Alto portals, followed the next day by SonicWall API scans.

GreyNoise Block users can automatically block all associated IPs through provided templates for Palo Alto and SonicWall activity, with enterprise customers able to apply more granular blocklists based on ASNs, JA4, and geography.

“Defenders should:
* Monitor authentication surfaces for abnormal velocity or repeated failures.
* Track recurring client fingerprints to surface campaign continuity.
* Apply dynamic, context-aware blocking rather than static reputation lists,” concludes the report.

To read the complete article see: [Security Affairs](https://securityaffairs.com/185382/hacking/attackers-launch-dual-campaign-on-globalprotect-portals-and-sonicwall-apis.html)