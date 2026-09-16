---
title: Iranian Cyber Targeting of Dissidents, Activists and Journalists
date: 2026-09-15
categories: [CYBERSECURITY]
tags: [IRAN,CYBERSECURITY,MALWARE,DISSIDENTS,ACTIVISTS]
---

## Iranian Cyber Targeting of Dissidents, Activists and Journalists

**Source:** UK NCSC  
**Date Published:** September 15, 2026  

The **CHOSEN BRICK** malware family has been utilized to target individuals globally, including in the UK, US, and the Netherlands, since at least 2025. This malware enables Iranian state cyber actors to gather information on a target's contacts, emails, and social media messages, potentially allowing them to track movements. Iran likely employs cyber activities to suppress individuals perceived as threats to the regime, such as dissidents, activists, and journalists. The personal details of some previous victims have surfaced on pro-Iranian leak sites, heightening the risk to their safety.  

This advisory from the UK National Cyber Security Centre, the US Federal Bureau of Investigation, and the Netherlands' General Intelligence and Security Service (AIVD) provides technical information about the malware, tactics, techniques, and procedures (TTPs), along with advice for individuals and organizations.  

Iranian cyber actors engage with targets through social messaging applications to establish rapport before attempting to deliver the malware. They often pose as someone familiar to the target or as technical support from the messaging platform. This rapport is used to persuade the target to download and open a file that appears legitimate. These files may masquerade as applications like Pictory, RunwayML, Norton Antivirus, Telegram, Adobe Flash Player, or even as MRI scan results. Notably, the malware has been exclusively aimed at the Windows operating system.  

**Persistence and Evasion**  
CHOSEN BRICK is designed to persist through device reboots by utilizing registry keys, primarily the Run key in "HKCU \ Software \ Microsoft \ Windows \ CurrentVersion \ Run". It adds exclusions to Microsoft Defender antivirus to evade detection. Once installed, the malware connects to Telegram for Command and Control, enabling a wide range of commands, including capturing screen and audio content, stealing emails, and wiping the system. Data is exfiltrated through Telegram bots and cloud object stores. Recent variations of this malware also employ HTTPS/SOCKS5 proxies to obscure their activities.  

**Recommendations for Organizations**  
Organizations suspecting CHOSEN BRICK execution should contact their IT providers for investigation. As this malware targets personal devices, organizations are advised to inform staff likely to be targeted and assist them in checking their personal devices.  

**Example Malicious Entries**  
Malicious entries associated with CHOSEN BRICK include:  
- Value name 'SMQDService' with data 'C: \ ProgramData \ SMQDServicePackages \ ... \ smdqservice.exe'  
- Value name 'winappx' with data 'C: \ Users \ All Users \ MicrosoftDistribution \ sysmain \ winappx.exe'  

**Domains to Investigate**  
Domains that should be investigated further include:  
- api[.]telegram[.]org  
- backblazeb2[.]com  
- vultrobjects[.]com  
- storjshare[.]io  
- iproyal[.]com  
- lightningproxies[.]net  

For more detailed information, please refer to the full article: [Read full article](https://www.ncsc.gov.uk/news/iranian-cyber-targeting-of-dissidents-activists-and-journalists)  
