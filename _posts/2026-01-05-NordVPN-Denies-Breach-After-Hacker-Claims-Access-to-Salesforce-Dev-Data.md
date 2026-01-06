---
title: NordVPN Denies Breach After Hacker Claims Access to Salesforce Dev Data
date: 2026-01-05
categories: [SECURITY]
tags: [NORDVPN,HACKER,SALESFORCE,BREACH,SECURITY]
---

A hacker using the alias 1011 has claimed to breach a NordVPN development server, posting what appears to be database dumps and configuration samples on the latest version of BreachForums. The leak was shared under the title "nordvpn.com SalesForce - leaked, Download!" and was accompanied by claims that access was gained by brute-forcing a misconfigured system. The post included what the actor described as Salesforce API keys, Jira tokens, and source code from over ten databases. A screenshot shared by the hacker displayed data structure and field names suggesting it could be from a development environment, but there’s nothing in the screenshot that clearly links it to NordVPN beyond the hacker’s label.

NordVPN quickly responded, stating that their internal systems have not been compromised. In a blog post published the same day, the company addressed the claims head-on and explained what they believe the leak actually contains. According to NordVPN, the files originate from a test environment set up six months ago during the evaluation of a third-party platform. The trial was short-lived, no contract was signed, and no production systems were connected during the process. The company clarified that no sensitive customer information, real API keys, or internal source code were ever shared with that vendor.

Their blog emphasized that the environment shown in the leak wasn’t part of their active Salesforce infrastructure. Instead, it was an isolated sandbox used briefly to assess automated testing tools. NordVPN said that the data in question included only dummy content and was never used in any live service. While the hacker framed the post as a serious breach involving NordVPN’s core systems, the company disputes the connection entirely. They’re confident the data was from a third-party system used temporarily during a trial period that has long since ended. They’ve also reached out to that vendor for further clarity.

At this point, there’s no verifiable link between the samples shared by the hacker and any production environment at NordVPN. The company continues to monitor the situation and stated that no customer action is needed.

To read the complete article see: [Hackread](https://hackread.com/nordvpn-denies-breach-hacker-salesforce-dev-data/).