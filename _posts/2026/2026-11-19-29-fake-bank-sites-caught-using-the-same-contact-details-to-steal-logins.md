---
title: 29 Fake Bank Sites Caught Using the Same Contact Details to Steal Logins
date: 2026-11-19
categories: [CYBERSECURITY]
tags: [PHISHING,CYBERCRIME,BANKING,SECURITY]
---

## 29 Fake Bank Sites Caught Using the Same Contact Details to Steal Logins 🚨

A recent phishing campaign uncovered by Netskope Threat Labs has revealed that cybercriminals are creating fictional yet convincing bank websites. These sites, equipped with account-opening pages, customer support details, and online banking portals, are generated using a simple PHP script. Over a span of seven weeks, starting in late September 2026, around **29 fake bank domains** emerged, featuring names like **Sunray Trust**, **Quartz Bank**, **Western Future Bank**, and **Apex Trust Financial Bank**. These pages are designed to collect login credentials and personally identifiable information (PII), including names and addresses.

Geographically, **North America** has seen the highest number of affected organizations, followed by **Europe** and **Asia**. Notably, finance and banking organizations accounted for nearly half of the victims.

### Identical Templates and Deceptive Practices 🔍

While these fake banking sites may appear as separate financial institutions to unsuspecting visitors, Netskope found that they share the same underlying template. Their layouts, marketing text, support number (1-800-BANKING), and even bank routing numbers are strikingly similar, with only minor variations. For instance, one deployment changed a digit in the routing number from **251480576** to **981480576**. 

Netskope Threat Labs traced these sites back to a single phishing kit, which provided scammers with a ready-made banking website complete with login and account-opening forms designed to harvest passwords and personal information. A detail left behind on the now offline **Quartz Bank** website (qtbnk.com) hinted at the origins of these pages, showcasing a logo with the original template branding: "EMENDY INVEST, Bitcoin, forex investment and trading PHP script."

### The Scammers' Strategy 💡

Researchers believe that the operators acquired or traded a ready-made PHP banking script and reused it under different bank names. They also utilized low-cost or abuse-friendly domain extensions, including **.sbs**, **.cc**, **.pro**, **.live**, **.online**, and **.info**. To enhance their credibility, scammers have gone to great lengths to make these fictional banks appear established. For example, **Bray Finance** was listed as a contact on a real estate website, while another fake bank was linked directly to its phishing domain on a business information site. Such tactics could help these names appear in search engines and AI-generated answers, giving victims another reason to trust them.

### Rapid Lifecycle of Fake Banks ⏳

Around one-third of the 29 domains had no VirusTotal detections when Netskope first discovered them, while the remaining domains averaged fewer than five detections across approximately 90 antivirus and URL-scanning engines. As Netskope researchers noted, "These sites live fast and die young," explaining that operators can abandon domains before reputation-based security tools have time to flag them. 

The crucial takeaway for defenders is that while the domain name may change, the website's underlying details remain consistent. Repeated routing numbers, contact information, and page elements can help expose the next fake bank even before security scanners recognize its domain.

For more details, check out the full article here: [Read full article](https://hackread.com/29-fake-bank-sites-using-contact-details-steal-logins/) 
