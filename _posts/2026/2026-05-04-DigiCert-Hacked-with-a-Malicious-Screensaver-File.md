---
title: DigiCert Hacked with a Malicious Screensaver File
date: 2026-05-04
categories: [CYBERSECURITY]
tags: [DIGICERT,MALWARE,CYBERATTACK,SCREENSAVER,SECURITY]
---

## DigiCert Hacked with a Malicious Screensaver File 🚨

A threat actor gained access to DigiCert's backend and stole **27 code signing certificates** that were later used to sign malware. The incident took place last month and was traced back to a **social engineering attack** that successfully compromised two employees of DigiCert's tech support team.

According to DigiCert's post-mortem, the attacker posed as a customer and tricked the tech support staff into running an **SCR file**, a format used to install and configure Windows screensavers. DigiCert reports that the campaign was blocked on all but two of its tech support staff systems. On the first system, the attacker maintained access for less than a day, while on the second, they maintained access for almost two weeks due to a misconfiguration of the CrowdStrike EDR agent.

During this time, the attacker accessed tech support tickets for **EV certificates** that DigiCert was in the process of approving, stealing the future customer's **initialization code**. Possession of an initialization code, combined with an approved order, is sufficient to obtain the resulting certificate. The attacker was able to obtain these two pieces of information for a finite set of approved orders, leading to the acquisition of **EV Code Signing certificates** across a set of customer accounts and CAs.

DigiCert has since revoked all 60 orders for EV certificates processed during the attack, with 27 of the revoked certificates explicitly linked to the threat actor. The stolen certificates were used to sign payloads that delivered the **Zhong Stealer**, a malware family previously used by cybercrime groups involved in cryptocurrency thefts. This campaign was linked to **GoldenEyeDog (APT-Q-27)**, a well-known Chinese e-crime group, although it remains unclear if they were responsible for the DigiCert hack.

### Other Security News 🔒

In other security news, hackers have gained access to the source code of security firm **Trellix**. The company confirmed that no changes were made to any of its products and has notified law enforcement. Additionally, threat actors are exploiting a recent **cPanel vulnerability** to wipe public websites and post fake ransoms on their homepages, demanding **$8,000** paid in Bitcoin. Thousands of websites have been defaced, but no ransom has been paid into the attacker's wallet.

Furthermore, a major **DDoS attack** has disrupted most of the web infrastructure supporting the **Ubuntu** operating system. The attacks targeted several Ubuntu and Canonical domains and APIs, preventing users from installing or updating their operating systems. A pro-Palestinian hacktivist group named the **313 Team** claimed responsibility for the DDoS, which also previously targeted **BlueSky** and **Mastodon**.

Lastly, hackers have stolen **$5 million** worth of crypto assets from the **Wasabi Protocol** trading platform by compromising an admin and setting the delay on admin actions to zero, allowing for instant malicious transactions.

[Read full article](https://news.risky.biz/r/4a75538b)