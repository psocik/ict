---
title: WhatsApp device linking abused in account hijacking attacks
date: 2025-12-17
categories: [SECURITY]
tags: [WHATSAPP,ACCOUNT HIJACKING,GHOSTPAIRING,CYBERSECURITY]
---

**Source:** Bleeping Computer  

**Excerpt:**  
Threat actors are abusing the legitimate device-linking feature to hijack WhatsApp accounts via pairing codes in a campaign dubbed GhostPairing. This type of attack does not require any authentication, as the victim is tricked into linking the attacker’s browser to a WhatsApp device. By doing so, threat actors gain access to the full conversation history and shared media, and may leverage information to impersonate users or commit fraud. Gen Digital (formerly Symantec Corporation and NortonLifeLock) says that the campaign was first spotted in Czechia but warns that the propagation mechanism allows it to spread to other regions, with compromised accounts acting as springboards to reach new targets.  

The attack starts with a short message from a known contact, sharing a link allegedly leading to an online photo of the victim. To instill some trust, the link is displayed as a content preview from Facebook. Furthermore, the link takes the victim to a fake Facebook page hosted on typosquatted or similar-looking domains, which informs that users need to be verified by logging in before accessing the content. The verification page is deceptive and actually triggers WhatsApp’s device-pairing workflow. Victims are asked for their phone number, which the attacker uses to initiate a legitimate device-linking or login process.  

WhatsApp generates a pairing code that the attacker displays on the fake page. WhatsApp also prompts the victim to enter the code to link the new device to their account. While WhatsApp's message is clear that the notification is for an attempt to link a new device to the account, users are likely to miss it. Once the victim enters the pairing code, the attacker has complete access to the account without needing to bypass any protections. WhatsApp Web provides access to new messages in real time and allows viewing or downloading shared media. It can be used to send messages and forward the same lure to available contacts and groups. “Many victims are unaware that a second device has been added in the background, which is what makes the scam even more dangerous – criminals are hiding in your account, watching your every conversation without you even knowing it,” Gen Digital warns.  

The only way to uncover the compromise is to go to **Settings → Linked Devices**, and check for unauthorized devices linked to the account. Users are encouraged to block and report suspicious messages and activate two-factor authentication account protection. If you are rushed into taking action, you should always take your time, analyze the received message, if it makes sense, and if the person contacting you is indeed who they claim. It should be noted that linking devices is also possible by scanning a QR code using the mobile WhatsApp application. The feature is available in multiple messaging apps and has been exploited by Russian threat actors in the past to gain access to Signal accounts of interest.  

To read the complete article see: [Bleeping Computer](https://www.bleepingcomputer.com/news/security/whatsapp-device-linking-abused-in-account-hijacking-attacks/)  
