---
title: The Enemy Within Tracking LIMINAL PANDA and SilentAir
date: 2026-11-11
categories: [CYBERSECURITY]
tags: [LIMINAL PANDA,SILENTAIR,MOBILE NETWORKS,CYBER OPERATIONS,THREAT ACTORS]
---

## The Enemy Within: Tracking LIMINAL PANDA and SilentAir through Mobile Networks

In this blog, we outline the publicly reported, China-nexus **LIMINAL PANDA** threat actor's evolution in its attacks on mobile operator networks, focusing on its activity on the signalling interconnect network. We also outline malicious signalling activity that we have observed over the last 2 years from a new signalling threat actor, whom we term **SilentAir**, whose activity we also believe aligns with China-nexus cyber operations. 🚀

Sophisticated threat actors are compromising Mobile Network Operators to steal information and launch attacks on other operators and their subscribers. Enea detected ongoing activity in 2026 by **LIMINAL PANDA**, a previously identified threat actor. We also uncovered **SilentAir**, a newly identified actor compromising operators since before 2025. Links between the two are possible but unconfirmed.

### Targeted Regions

Taiwan is the primary target of **SilentAir**, but not the only one. We observed **SilentAir**-related sources in at least six Asian countries targeting a dozen additional countries and territories. Targets included political and government VIPs. The **SilentAir** attacks threaten calls, messages, privacy, and account security. Enea observed intercepted two-factor authentication codes immediately after interception for some targets, suggesting attempts to access other accounts. **LIMINAL PANDA** was detected operating across multiple operators, with Enea detecting hundreds of attempted covert communications. Evidence points to 5-10 infected operators, with dozens more potentially affected. Attacker activity includes stealthy compromise and information retrieval.

### GTPDoor Implant

**GTPDoor** is a Unix-based remote-access implant that uses the GTP-C protocol for covert command & control (C2) communications. It was first publicly reported and analyzed from two publicly available versions in February 2024. CrowdStrike assessed in November 2024 that **LIMINAL PANDA**'s activity "aligns with China-nexus cyber operations." Brandefence stated they assess with moderate confidence that some aspects of **LIMINAL PANDA** are operating on behalf of a regional bureau of China's Ministry of State Security (MSS). In July 2026, POST Luxembourg reported publicly that they had detected **GTPDoor** activity. We began to detect **GTPDoor** activity and other associated **LIMINAL PANDA** activity on the GTP-C interface in multiple customer mobile operators from Q1 2026 onwards. In total, we detected several hundred attempted covert C2 communications. We have directly observed or seen strong indications of at least 5 to 10 mobile operators infected, and our intelligence leads us to believe that there may be several dozen infected operators globally, with an emphasis on Asia, Africa, and Latin America.

The types of **GTPDoor**-transported commands we observed included:
- Starting/stopping communication & exfiltration tunnels
- Encapsulation of commands using other tools for lateral movement through the infected operator (using malware like **EchoBackdoor**)
- Initiation of other processes, including SSH commands.

Through our investigations, we subsequently uncovered evidence that **LIMINAL PANDA** uses a new **GTPDoor** version, specifically one that uses the GTP-U protocol, not GTP-C. We call this new version of the **GTPDoor** malware, **GTPDoor version 3** or **GTP-U-Door/GTPDoor(U)**. The use of **GTP-U** is a very significant development.

For more detailed information, you can read the complete article here: [Read full article](https://www.enea.com/insights/the-enemy-within-tracking-liminal-panda-and-silentair-through-mobile-networks/) 
