---
title: An Active Intrusion Campaign Against Check Point Security Management Servers
date: 2026-11-24
categories: [CYBERSECURITY]
tags: [INTRUSION,CHECK-POINT,SECURITY,CAMPAIGN,CYBER-ATTACK]
---

## An Active Intrusion Campaign Against Check Point Security Management Servers

🚨 **GreyNoise** recently discovered an intrusion campaign targeting Check Point Security Management Servers, with confirmed attack activity between **October 17th and November 2nd, 2026**, impacting at least **22 distinct organizations** globally. This set of threat activity is tracked as **GreyNoise Threat 13 (GT13)**, which represents adversary infrastructure, tools, and post-exploitation actions against the 22 victims.

The campaign does not appear to focus on any specific geography or industry sector. The impacted organizations include victims with assets in the **United Kingdom, Ireland, France, Netherlands, Greece, Germany, Austria, Bulgaria, Poland, India, Thailand, Vietnam, South Korea, Hong Kong, China, Australia, and the United States**. The sectors affected include **financial services, energy, government, transportation, mining, engineering, and manufacturing**. GreyNoise does not attribute GT13 to any known or publicly tracked threat group at this time.

### Attack Details

The actor used **99 IP addresses**, much of which were disposable network infrastructure to conduct scanning, exploitation, and control of its victims. This included the use of a compromised server acting as an **"operational relay box" (ORB)** or simply a **"hop"** for interacting with downstream victim assets. The actor utilized this relay box to save command results and data stolen from **24 distinct Check Point Security Management Servers**.

The actor employed tools such as **Nmap, Chisel, Impacket, and Paramiko** to perform intrusion activities against their victim assets, including attempts to perform internal reconnaissance, privilege escalation, and lateral movement. The threat actor exploited multiple **CVEs**, including:
- CVE-2026-61500 (Rejetto HFS)
- CVE-2025-5777 (Citrix NetScaler)
- CVE-2024-21893 (Ivanti)
- CVE-2026-41089 (Windows NetLogon)
- CVE-2026-16232 (Check Point SmartConsole auth bypass to Run Script)
- CVE-2026-98432 (Linux IPv4 UAF)

Though hands-on-keyboard activity was observed, researchers believe the actor used **LLMs and agentic systems** to perform vulnerability scanning, exploitation, tool development, and automated interaction with compromised assets. Our visibility into this attack activity stopped around **November 2nd, 2026**, but given the actor's persistent access to victim Check Point devices, this intrusion campaign is expected to be ongoing.

### Summary of Activities

The GT13 actor's activities involved **99 IP addresses**, either egresses through **ExpressVPN** or compromised victim Check Point devices, and included over **1400+ network sessions**, **800+ command line artifacts**, and **1200+ files downloaded, uploaded, or created**. The GT13 threat actor used an automated scanning and exploitation pipeline to compromise an HFS server using **CVE-2026-61500**. On **2026-10-02 13:17:45 UTC**, the actor scanned and began exploitation against the HFS server. Through conducting several logins in succession, the actor collected enough output to reconstruct the internal state of the **V8 PRNG algorithm**, thus recovering an HFS session-cookie signing key and forging a signed admin session cookie. This allows the attacker to log in as admin without a password.

Minutes later, by **2026-10-02 13:19:37 UTC**, admin requests with forged session cookies were observed, indicating exploitation of **CVE-2026-61500** for session forgery, which was not patched on this server. The actor now had control of the server.

For more details, check out the full article: [Read full article](https://www.greynoise.io/blog/check-point-security-management-servers-intrusion-campaign)