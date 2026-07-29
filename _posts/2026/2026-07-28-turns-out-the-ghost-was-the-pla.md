---
title: Turns Out the Ghost Was the PLA
date: 2026-07-28
categories: [CYBERSECURITY]
tags: [APT15,PLA,CYBERSECURITY,HACKING,INTRUSION]
---

## Turns Out the Ghost Was the PLA

Our research uncovered a tidy little overlap that points straight at APT15 and the PLA Cyberspace Force's 8th Technical Reconnaissance Base (8th TRB). This tool, known in the cybersecurity world as **RedRelay** (or **ORBWEAVER** if you prefer), is a favorite among Chinese state-backed hackers. A collection of eDiary files, a Chinese note-taking tool, provided a glimpse into the 8th TRB's activities. Open-source research showed that the customer listed as Unit 61046 was otherwise known as the 8th TRB and that their address was 遗光寺8号院. Curiously, many of the references mention Second Division, which appears to be the specific unit that this eDiary belonged to.

The eDiary wasn't just administrative fluff; it detailed comprehensive research on targets, including their networks and cryptographic capabilities. One particular page shows a draft report signed by the 8th TRB Third Section even contained a screenshot showing them searching the victim's mailbox for emails relating to a technical issue that was hampering their efforts. Many pages contained data extracted from victims using tools such as **mimikatz** and **impacket**. One page even had 10MB of credentials from the Royal Thailand Armed Forces, probably enough to account for all serving members. The Chinese military maintained high-level access to government departments all over the world. The file list reads more like a Who's Who of Belt and Road nations in Africa.

To connect APT15, researchers included attribution terms in their searches. One of the items on the list was **vpnkerio**, which is a domain believed to be used exclusively by APT15 for their campaign targeting the Middle East and Africa. A hit for this search term was found in the same eDiary file that contains all those links to the 8th TRB. The eDiary contained page after page of commands used to gain initial access to their victims. All of them contain the same steps: a python script uses **CVE-2020-0688** to execute commands on the victim. These commands force the victim to connect to an IP address associated with vpnkerio[.]com and download a file called **kerio.exe**. The same script is used to create a webshell on the victim server. The list of victims also has significant overlap with known APT15 targets.

Thus, either the 8th TRB is using the same infrastructure as APT15 to hack into the same targets as APT15, or the 8th TRB is APT15. The eDiary provided evidence that the 8th TRB is responsible for APT15 activity. This evidence shows that victims of APT15 attacks have actually been on the receiving end of Chinese military cyber operations. While the eDiary contained nothing of RedRelay, researchers know that the 8th TRB/APT15 does use it. This indicates the type of activity companies like Guangdong Chanming are enabling.

[Read full article](https://intrusiontruth.wordpress.com/2026/07/28/turns-out-the-ghost-was-the-pla/)