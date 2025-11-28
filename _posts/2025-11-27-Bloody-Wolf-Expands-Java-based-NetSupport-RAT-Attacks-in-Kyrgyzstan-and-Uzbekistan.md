---
title: Bloody Wolf Expands Java-based NetSupport RAT Attacks in Kyrgyzstan and Uzbekistan
date: 2025-11-27
categories: [CYBERSECURITY]
tags: [KYRGYZSTAN,UZBEKISTAN,NETSUPPORT RAT,BLOODY WOLF,CYBERATTACKS]
---

Bloody Wolf, an actor active since at least late 2023, is expanding its operations in Central Asia, now targeting Kyrgyzstan and Uzbekistan with the NetSupport RAT. The group has been active since at least June 2025 in Kyrgyzstan and expanded to Uzbekistan as of October 2025. The targets include entities in the finance, government, and IT sectors. This campaign relies on social engineering and readily available tools to maintain effectiveness while keeping a low profile.  

The attacks involve impersonating government entities, specifically the Ministry of Justice, via official-looking PDF documents and domain names. These documents host malicious Java Archive (JAR) files designed to deploy the NetSupport RAT. The spear-phishing attacks trick recipients into clicking links that download the malicious JAR loader files, along with instructions to install Java Runtime, masking the true purpose of executing the loader.  

Once launched, the JAR loader fetches the NetSupport RAT payload from attacker-controlled infrastructure and establishes persistence through three methods: creating a scheduled task, adding a Windows Registry value, and dropping a batch script to the "%APPDATA%\Microsoft\Windows\Start Menu\Programs\Startup" folder. The Uzbekistan campaign includes geofencing restrictions, redirecting requests from outside the country to the legitimate data.egov[.]uz website, while requests from within Uzbekistan trigger the JAR file download from an embedded link within the PDF attachment.  

The JAR loaders are built with Java 8, suggesting the attackers may be using a custom JAR generator or template to create these artifacts. The NetSupport RAT payload is an older version of NetSupport Manager from October 2013. This shows that Bloody Wolf is leveraging older software versions in their attacks.  

Group-IB highlights that Bloody Wolf uses low-cost, commercially available tools to carry out targeted cyber operations. By exploiting trust in government institutions and leveraging simple JAR-based loaders, the group continues to maintain a foothold in the Central Asian threat landscape. Security teams should focus on user awareness training to spot phishing emails and proactively monitor for the creation of suspicious scheduled tasks or registry entries. Patching Java runtimes is also essential.  

To read the complete article see: [The Hacker News](https://thehackernews.com/2025/11/bloody-wolf-expands-java-based.html) 