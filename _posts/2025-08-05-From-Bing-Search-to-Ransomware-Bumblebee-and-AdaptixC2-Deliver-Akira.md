---
title: From Bing Search to Ransomware Bumblebee and AdaptixC2 Deliver Akira
date: 2025-08-05
categories: [RESEARCH]
tags: [MALWARE,BUMBLEBEE,AKIRA,CYBERSECURITY]
---

Bumblebee malware has been an initial access tool used by threat actors since late 2021. In 2023 the malware was first reported as using SEO poisoning as a delivery mechanism. Recently in May of 2025, Cyjax reported on a campaign using this method again, impersonating various IT tools. We observed a similar campaign in July in which a download of an IT management tool ended with Akira ransomware.

In July 2025, we observed a threat actor compromise an organization through this SEO poisoning campaign. A user searching for “ManageEngine OpManager” was directed to a malicious website, which delivered a trojanized software installer. This action led to the deployment of the Bumblebee malware, granting the threat actor initial access to the environment. The intrusion quickly escalated from a single infected host to a full-scale network compromise.

Following initial access, the threat actor moved laterally to a domain controller, dumped credentials, installed persistent remote access tools, and exfiltrated data using an SFTP client. The intrusion culminated in the deployment of Akira ransomware across the root domain. The threat actor returned two days later to repeat the process, encrypting systems within a child domain and causing significant operational disruption across the enterprise.

This campaign affected multiple organizations during July as we received confirmation of a similar intrusion responded to by the Swisscom B2B CSIRT in which a malicious IT tool dropped Bumblebee and also ended with Akira ransomware deployment.

To read the complete article see:
[DFIR Report](https://thedfirreport.com/2025/08/05/from-bing-search-to-ransomware-bumblebee-and-adaptixc2-deliver-akira) 


***

***Working at Team Cymru is more than a job — it’s a chance to be part of something meaningful.
Enjoy outstanding benefits, work with incredible people, and contribute to a mission that truly matters.

Explore open roles and join us:
[Team Cymru Careers](https://www.team-cymru.com/careers) 
