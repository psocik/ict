---
title: Fake Minecraft Sites Are Still Spreading WeedHack After C2 Takedown
date: 2026-08-25
categories: [MALWARE]
tags: [MINECRAFT,MALWARE,CYBERSECURITY,WEEDHACK]
---

## Fake Minecraft Sites Are Still Spreading WeedHack After C2 Takedown 🚨

McAfee Labs has released a follow-up report on the **WeedHack Malware-as-a-Service** campaign, revealing that ten active malicious sites and several file-hosting accounts continue to spread this infostealer despite a disruption to its command-and-control infrastructure. Over the past month, McAfee WebAdvisor blocked more than **6,300 user attempts** to access these sites. 

WeedHack was first identified in early June 2026, when McAfee researcher **Aayush Tyagi** documented a Malware-as-a-Service operation that had been running since January, affecting **116,464 systems** and adding between **2,000 and 3,000 new victims** daily. The original article was published in July, and since then, there has been a noticeable disruption in WeedHack's campaign, as its C2 server is no longer active. However, attackers have shifted their tactics. 

The operation offered a **free tier** accessible to anyone with a Discord account, a **premium tier** with webcam surveillance for just **$5 a month**, and a dashboard for operators to view stolen credentials and monitor victims in real-time. The malware spread through fake Minecraft client websites, YouTube videos linking to malicious downloads, and SEO poisoning, pushing these fake sites to the top of search results for popular Minecraft tools. 

The malware is capable of stealing session cookies, passwords, browser data, and cryptocurrency wallet contents. It employs **EtherHiding**, a technique that retrieves the attacker's active server address from the Ethereum blockchain, ensuring continued contact with its infrastructure even when individual servers are taken down. 

During the investigation, it was noted that many of these websites appeared legitimate, often mimicking real sites. A series of brand-impersonation attacks targeted several popular Minecraft clients, with fake websites replicating the real tool's features, FAQs, installation steps, and even links to legitimate GitHub repositories. 

Researchers found that the first two Google results for **"Xenon Client"**, a popular Minecraft client, led to fake sites distributing WeedHack. The campaigns exploit a structural weakness in the Minecraft modding community, where many popular tools lack official websites, relying only on GitHub pages and Discord servers. One notable fake site, **nova-client.com**, was built to rank above the genuine GitHub repository. 

McAfee discovered that most malicious links originated from **Discord (49.6%)**, followed by **MediaFire (23.4%)**, **GitHub (8.2%)**, and **Dropbox (4.6%)**. The campaign also infiltrated trusted Minecraft communities like **Planet Minecraft** and **EndMods**, making the scams harder to detect. 

**Recommendations:** McAfee advises users to download mods and clients only from official developer repositories or trusted platforms such as **Modrinth** and **CurseForge**. If a tool requests you to disable antivirus protection, treat it as malware. 

For more details, check out the full article: [Read full article](https://securityaffairs.com/197784/malware/fake-minecraft-sites-are-still-spreading-weedhack-after-c2-takedown.html)