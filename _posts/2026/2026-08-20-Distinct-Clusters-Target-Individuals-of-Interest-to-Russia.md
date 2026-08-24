---
title: Distinct Clusters Target Individuals of Interest to Russia
date: 2026-08-20
categories: [CYBERSECURITY]
tags: [RUSSIA,CYBER ESPIONAGE,PHISHING,GOOGLE CLOUD,THREAT INTELLIGENCE]
---

## Distinct Clusters Target Individuals of Interest to Russia

The **Google Threat Intelligence Group (GTIG)** is tracking three distinct suspected Russian cyber espionage threat clusters that are abusing legitimate authentication flows to target individuals working in **academia**, **aerospace and defense**, **governments**, and **think tanks** across Europe, as well as in the United States. 🚀

We now track an additional two distinct suspected Russian clusters, **UNC7005** and **UNC5976**, which conduct phishing, abuse OAuth flows, and/or deploy malware to victims. While each group conducts their campaigns differently, they all ultimately demonstrate a focus on the abuse of legitimate authentication workflows to compromise accounts. GTIG assesses with high confidence that these three threat clusters - **UNC6293**, **UNC7005**, and **UNC5976** - possess a Russian nexus, based on high-level targeting patterns, phishing themes, and shared operational techniques.

### Recent Activities

- **UNC6293** operations were initially reported in **June 2025** as an aggressive app password phishing campaign against prominent individuals critical of Russia. In these cases, attackers attempt to convince targets to set specific app passwords on their accounts, which they then use to gain access without needing two-factor authentication (2FA).
- In **October 2025**, GTIG observed **UNC6293** using a PDF lure document that contained the same screenshots as observed in June 2025, including the **ms.state.gov** reference.
- In early **August 2026**, **UNC7005** began Google account OAuth phishing operations using cloud infrastructure. An earlier attacker-controlled domain spoofing Microsoft in **April 2026** was used by **UNC7005** as C2 for malware we call **ENGINELIGHT**.

GTIG also observed **UNC5976** leverage a malicious Excel plugin, **HEADRUSH**, in **April 2026**, which ultimately led to an HTML Application (HTA) downloader.

For more detailed information, please visit the full article: [Read full article](https://cloud.google.com/blog/topics/threat-intelligence/distinct-clusters-target-individuals-of-interest-to-russia)