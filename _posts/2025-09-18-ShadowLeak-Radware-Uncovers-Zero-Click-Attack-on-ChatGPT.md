---
title: ShadowLeak Radware Uncovers Zero-Click Attack on ChatGPT
date: 2025-09-18
categories: [SECURITY]
tags: [CHATGPT,RADWARE,ZERO-CLICK ATTACK,CYBERSECURITY]
---

Researchers at Radware uncovered a server-side data theft attack targeting ChatGPT, called ShadowLeak. The experts discovered a zero-click vulnerability in ChatGPT’s Deep Research agent when connected to Gmail and browsing. The researchers explained that using a crafted email could trigger the agent to leak sensitive inbox data to an attacker with no user action or visible UI.

Service-Side Exfiltration: Unlike prior research that relied on client-side image rendering to trigger the leak, this attack leaks data directly from OpenAI’s cloud infrastructure, making it invisible to local or enterprise defenses. The attack utilizes an indirect prompt injection that can be hidden in email HTML (tiny fonts, white-on-white text, layout tricks) so the user never notices the commands, but the agent still reads and obeys them.

Service-side attacks pose greater risk than client-side leaks: enterprise defenses can’t detect exfiltration because it runs from the provider’s infrastructure, and users see no visible signs of data loss. The agent acts as a trusted proxy, sending sensitive data to attacker-controlled endpoints, and unlike client-side protections that limit exfil targets, these server-side requests face fewer URL restrictions, letting attackers export data to virtually any destination.

The PoC devised by the experts used Gmail, but the same attack works across any Deep Research connector. Files or messages in Google Drive, Dropbox, SharePoint, Outlook, Teams, GitHub, HubSpot, Notion and similar can hide prompt-injection payloads (in content or metadata) or malicious meeting invites, letting attackers trick the agent into exfiltrating contracts, meeting notes, customer records and other sensitive data. Any connector that feeds text into the agent becomes a potential vector. 

To read the complete article see: [Security Affairs](https://securityaffairs.com/182334/hacking/shadowleak-radware-uncovers-zero-click-attack-on-chatgpt.html) 

🌐 **Read more**: [Security Affairs](https://securityaffairs.com/182334/hacking/shadowleak-radware-uncovers-zero-click-attack-on-chatgpt.html)