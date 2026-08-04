---
title: Alleged Żabka Breach Exposes Jira Data, Source Code, and API Keys
date: 2026-08-03
categories: [DATA BREACH]
tags: [ZABKA,DATA BREACH,JIRA,SOURCE CODE,API KEYS]
---

## Alleged Żabka Breach Exposes Jira Data, Source Code, and API Keys

🚨 An alleged data leak from Żabka, Poland's largest convenience store operator, has surfaced, offering a treasure trove of sensitive information for €5,000. This leak includes **Jira data**, **GitLab repositories**, and critical **API keys**. Researchers have verified much of the sample, raising serious concerns about the integrity of the data.

A new forum account appeared on **August 2, 2026**, posting a single message and asking for five grand for what it claims is a complete data dump from Żabka Polska. Ransomnews reviewed the sample archive attached to the listing and found that the numbers the seller bragged about mostly check out. However, Żabka itself has not confirmed any details regarding the breach.

### Key Findings:
- The listing claims to contain approximately **541,000 Jira issues** and nearly **230,000 IT service-desk tickets**.
- Source code from **89 GitLab repositories** is also included.
- Real internal systems are named, including Żabka's point-of-sale platform **Nowa Kasa**, **Cyberstore**, and **SAP ERP**.

Ransomnews confirmed that the counts for Jira issues and IT service-desk tickets matched almost exactly. However, some of the more sensational claims, such as **35,206 GDPR references** and roughly **4,000 bank account mentions**, were notably absent from the sample.

### Critical Concerns:
The most alarming aspect of this breach is a single **GitLab access token**, embedded in the clone URL of every repository dump. This token, if real and still active, could potentially allow unauthorized access to Żabka's entire cs-market platform. The repositories also contained sensitive secrets, including **Cloudflare API keys** and a **MongoDB admin password**.

### Timing of the Leak:
The leak's timing is particularly noteworthy, occurring just two days after **Alimentation Couche-Tard** announced a €7.56 billion offer for Żabka Group on **July 31**. While Ransomnews found no direct evidence linking the two events, the coincidence raises eyebrows.

### Conclusion:
As the investigation unfolds, it is crucial for Żabka to act swiftly. Rotating a token takes mere minutes, but discovering that it has been quietly cloning your entire codebase for an extended period can lead to significant damage. 

For more detailed information, you can read the full article [here](https://securityaffairs.com/196510/data-breach/alleged-zabka-breach-exposes-jira-data-source-code-and-api-keys.html).