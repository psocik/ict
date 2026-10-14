---
title: Kris McConkey on X Insights into RedRelay and APT15
date: 2026-10-13
categories: [CYBERSECURITY]
tags: [APT15,REDRELAY,MALWARE,CYBERSECURITY,IOT]
---

## Kris McConkey on X: Insights into RedRelay and APT15

🚀 Having previously posted that this was an interesting rabbit hole, a spam account liking that post a couple of weeks ago reminded me that I never actually explained why. So here's a brief version.

We first encountered **RedRelay** in early 2021 while responding to a ransomware incident at a European MSP. During this incident, we identified **APT15** in the network, which was routing their activity via a cluster of infrastructure that had significant communications between nodes via **UDP port 5500**. We soon discovered other clusters used by different actors, indicating that this was a shared capability, leading us to name it **RedRelay**. APT15 targets via RedRelay initially showed a vast spread across government, defense, and education organizations primarily in Europe and LATAM.

### Key Findings
- RedRelay binaries shared a distinctive shell command, a pre-shared-key hashing routine, and general architecture with the **FCN VPN tool**, authored by **boywhp**. This name is also linked to **Exforel** and **Daxin** malware. The original FCN GitHub repository was removed in 2020.
- We assessed that RedRelay's developer had access to FCN source code. Our insights allowed us to actively scan for nodes, illuminating over **1100 RedRelay hosts** scattered worldwide.
- Early FCN TLS certificates contained 'boywhp' and an email address, leading us to many others.

### Registration Data
Registration data for **xfconnect[.]com**, emails, and phone numbers pointed to a Guangzhou-based individual named **Wang Huiping**. We identified ties to **Guangdong Chanming**, a company registered in 2016 as **Guangzhou Chanming** before being renamed, where he is a shareholder along with CEO **Dai Zhaojun**. We found a modified FCN client branded as **STN Security Tunnel**. Chanming's registered product was **Security Tunnel Net**, described as an anti-traceability system. Multiple acronyms from company materials appeared in our technical RedRelay analysis, leading us to attribute the RedRelay service to Chanming in early 2022.

### Conclusion
The CEO presented about the company's "High concealment and anti-traceability control technology for IoT devices" at a 2019 conference in Wuhan, which was particularly insightful. Guangdong Chanming sells various products, including fully featured malware platforms, to government clients, such as those in **Qingdao**, where the likes of **Tick**, previously attributed to **Unit 61419**, are based. Company recruitment advertisements specifically request experience working with **PLA**, **MSS**, or **MPS**.

To read the complete article see: [Read full article](https://x.com/smoothimpact/status/2110012110130295012) 
