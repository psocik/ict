---
title: KONNI Adopts AI to Generate PowerShell Backdoors
date: 2026-01-22
categories: [SECURITY]
tags: [AI,POWERSHELL,KONNI,PHISHING]
---

Check Point Research (CPR) identified an ongoing phishing campaign that we associate with KONNI, a North Korean–linked threat actor active since at least 2014. KONNI is best known for targeting organizations and individuals in South Korea, focusing on diplomatic channels, international relations, NGOs, academia, and government. The group typically relies on spear-phishing that delivers weaponized documents themed around geopolitical issues and activity on the Korean Peninsula.

While the delivery and staging steps align with KONNI’s established tradecraft, the campaign shows signs of broader targeting across the APAC region, extending beyond the group’s usual focus areas. Another notable aspect of the campaign is its use of an AI-written PowerShell backdoor, reflecting the increasing adoption of AI-enabled tooling by threat actors, including North Korean–linked groups.

While clean structure and comments alone are not sufficient to attribute AI origins, the script contains a far more telling indicator. Embedded directly in the code is the comment: “# <– your permanent project UUID.” This phrasing is highly characteristic of LLM-generated code, where the model explicitly instructs a human user on how to customize a placeholder value. Such comments are commonly observed in AI-produced scripts and tutorials.

The PowerShell backdoor begins execution with a series of anti-analysis and sandbox-evasion checks. These include validating that the host meets minimum hardware thresholds and actively scanning for the presence of analysis and monitoring tools such as IDA, Wireshark, Procmon, etc. In addition, the backdoor enforces user-interaction checks by monitoring mouse activity and requires a minimum number of clicks before continuing. If these conditions are not met, the script terminates immediately.

To read the complete article see: [KONNI targets developers with AI malware](https://research.checkpoint.com/2026/konni-targets-developers-with-ai-malware/) 