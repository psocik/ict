---
title: Pulling Back the Curtain on Warlock's Next Act
date: 2026-02-11
categories: [CYBERSECURITY]
tags: [WARLOCK,RANSOMWARE,CYBERSECURITY,VULNERABILITIES]
---

## Pulling Back the Curtain on Warlock's Next Act

The ransomware group known as **Warlock**, also tracked as Storm-2603 and Gold Salem, has been quietly continuing its campaigns targeting edge devices and services. Warlock made headlines in the last several weeks, thanks in large part to an excellent post from Huntress on February 8th. Warlock last posted to its data leak site in November 2025, when it claimed 17 victims. 

Behind the scenes, Warlock has been expanding initial access methods, targeting more than 200 victims in at least 40 countries across a range of vulnerable edge devices. The targeted services include vulnerable SmarterTools SmarterMail servers, SolarWinds Web Help Desk instances, and Gladinet CentreStack instances, among others. Black Lotus Labs has been following Warlock as their infrastructure and targeting has shifted over time, while simultaneously protecting customers and engaging with law enforcement. 🚀

Warlock’s recent activity underscores a growing trend: ransomware crews rapidly weaponizing newly disclosed vulnerabilities to scale their operations globally. Victims targeted in recent Warlock campaigns include entities in the education, technology, energy, and nonprofit sectors, as well as government entities across the world. As disclosed by Huntress, Warlock’s most recent campaign impacts entities running SolarWinds Web Help Desk, especially those with vulnerabilities like CVE-2025-40551. Additionally, SmarterTools publicly disclosed their own Warlock compromise on January 29th, targeting an exposed SmarterMail server. CISA recently added SmarterMail CVE-2026-24423 to its Known Exploited Vulnerabilities catalog, indicating that it was known to be used in ransomware campaigns. Black Lotus Labs’ IP backbone telemetry first identified Warlock targeting SmarterMail services at scale on January 25th.

We can confirm Huntress’ finding that Warlock uses v2-api[.]mooo[.]com for victim communications. This domain was most recently hosted on 198.13.158[.]135. Black Lotus Labs also has evidence of Warlock targeting Gladinet CentreStack and continued targeting of Microsoft SharePoint servers. A Gladinet CentreStack vulnerability was identified in December as CVE-2025-14611, and Warlock has been known to target SharePoint services through vulnerabilities such as CVE-2025-53770. Other victims identified in Black Lotus Labs’ telemetry were hosting SonicWALL, Fortinet, and Check Point services, indicating broader targeting of commercial environments.

We echo the messages of Huntress and SmarterTools – patch vulnerable devices immediately, scan networks for downloads from catbox[.]moe, search for Velociraptor and Zoho installs not authorized by company policy, and maintain awareness for outbound connections to failover C2s hosted on BitLaunch. For Defenders, the following are C2 nodes associated with Warlock's infrastructure, observed over the last 90 days: 198.13.158[.]135, 162.252.198[.]197, 199.217.99[.]149.

To read the complete article see: [Read full article](https://www.linkedin.com/pulse/pulling-back-curtain-warlocks-next-act-blacklotuslabs-lduze)