---
title: DeepSeek Deception Sainbox RAT & Hidden Rootkit Delivery
date: 2025-06-26
categories: [APT]
tags: [NETSKOPE,SAINBOX RAT,HIDDEN ROOTKIT,CYBERSECURITY,PHISHING]
---

**Summary**  
Netskope Threat Labs has discovered a campaign using fake installers to deliver the Sainbox RAT and a Hidden rootkit. During our threat hunting activities, we encountered multiple installers disguised as legitimate software, including WPS Office, Sogou, and DeepSeek. These installers were mainly MSI files that were delivered via phishing websites. Both the phishing pages and installers were in Chinese, indicating that the targets are Chinese speakers. We can attribute this attack to Silver Fox, a China-based adversary group, with medium confidence based on the TTPs, particularly the phishing websites, the fake installers for popular Chinese software, the use of Gh0stRAT variants, and the targeting of Chinese speakers.

In this blog post, we’ll explore how the MSI payload is delivered, loaded, and executed in the victim’s machine.

**Key findings**  
- Netskope Threat Labs has discovered a new campaign using fake installers for popular software, including Sogou and DeepSeek, to target Chinese speakers with malware.  
- The malware payloads include the Sainbox RAT, a variant of Gh0stRAT, and a variant of the open-source Hidden rootkit.  
- Based on the nature of the campaign, the payloads involved, and the users being targeted, we can attribute these activities with medium confidence to the Silver Fox group.  

To read the complete article see: [https://www.netskope.com/blog/deepseek-deception-sainbox-rat-hidden-rootkit-delivery](https://www.netskope.com/blog/deepseek-deception-sainbox-rat-hidden-rootkit-delivery)  
