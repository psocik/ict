---
title: Several Dozen' High-Value Corporations Targeted by New Extortion Crew
date: 2026-04-09
categories: [CYBERSECURITY]
tags: [PHISHING,EXTORTION,CYBERSECURITY,DATA BREACH]
---

## New Extortion Crew Targets Corporations 🚨

A new extortion crew has targeted **several dozen high-value** corporations through phishing and helpdesk social-engineering, according to Google. The Google Threat Intelligence Group tracks this financially motivated group as **UNC6783**, which may have ties to the **Raccoon** persona. Principal threat analyst **Austin Larsen** stated, "We are aware of several dozen high-value corporate entities targeted across multiple sectors," adding that Google is aware of several successful attacks as part of this campaign.

### Attack Methodology 🔍

UNC6783 primarily compromises call centers and business process outsourcers (BPOs) that work with larger companies. This attack method has been popularized by groups like **Scattered Spider** and **ShinyHunters**. Once the criminals gain access to the BPOs' networks, they can use stolen legitimate credentials from BPO employees to infiltrate their customers' IT environments.

Google has also observed the extortionists targeting corporations' support and helpdesk staff directly to gain access and steal sensitive data. 

### Social Engineering Tactics 💻

Larsen explained, "The campaign relies on social engineering via live chat to direct employees to malicious, spoofed Okta login pages." These domains often masquerade as the targeted organization using a domain pattern such as `<org>[.]zendesk-support&lt;##>[.]com`. The attackers employ a custom phishing kit to bypass multi-factor authentication (MFA) by stealing clipboard contents, and then enroll their own devices for persistent access to victim environments. 

Additionally, Google has spotted the miscreants using fake security software updates to trick victims into downloading remote access malware. Once they steal corporations' data, the crew uses **Proton Mail** accounts to deliver ransom notes to their victims.

### Recent Breaches 📉

Last week, **International Cyber Digest** reported that **Adobe** was allegedly breached by an attacker calling themselves **Mr. Raccoon**. This attacker reportedly gained access through an Indian BPO by first deploying a remote access tool on one employee and then phishing that worker's manager. The data thief claimed to have stolen **13 million support tickets** with personal data, **15,000 employee records**, all **HackerOne submissions**, internal documents, and other information.

[Read full article](https://www.theregister.com/2026/04/09/several_dozen_highvalue_corporations_targeted/)