---
title: Behind the Clouds Attackers Targeting Governments in Southeast Asia Implement Novel Covert C2 Communication
date: 2025-07-14
categories: [RESEARCH]
tags: [CYBERSECURITY,GOVERNMENT,SOUTHEAST ASIA,CLOUD SERVICES]
---

Since late 2024, Unit 42 researchers have been tracking a cluster of suspicious activity as CL-STA-1020, targeting governmental entities in Southeast Asia. The threat actors behind this cluster of activity have been collecting sensitive information from government agencies, including information about recent tariffs and trade disputes.

This campaign is particularly noteworthy due to its novel tradecraft. The threat actors have developed a previously undocumented Windows backdoor, which we named HazyBeacon.

This backdoor leverages AWS Lambda URLs as command and control (C2) infrastructure. AWS Lambda URLs are a feature of AWS Lambda that allows users to invoke serverless functions directly over HTTPS. This technique uses legitimate cloud functionality to hide in plain sight, creating a reliable, scalable and difficult-to-detect communication channel.

In this analysis, we aim to provide security teams with the necessary insights to detect and mitigate this emerging threat, while contributing to the broader understanding of how attackers exploit cloud services for malicious purposes.

To read the complete article see: [Link to the full article](https://unit42.paloaltonetworks.com/windows-backdoor-for-novel-c2-communication/) 