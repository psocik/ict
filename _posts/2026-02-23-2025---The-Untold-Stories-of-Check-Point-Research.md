---
title: 2025 - The Untold Stories of Check Point Research
date: 2026-02-23
categories: [CYBERSECURITY]
tags: [CHECK POINT RESEARCH,CYBER THREATS,2025,SECURITY]
---

## 2025 - The Untold Stories of Check Point Research

Check Point Research (CPR) continuously tracks threats, following the clues that lead to major players and incidents in the threat landscape. A large portion of what we uncover remains in the shadows but is used on a day-to-day basis to improve protections, connect the dots between incidents, and keep a watchful eye on known threat actors and infrastructure. 🚀

In 2025, the activity varied by region and objective. In the Americas, attackers invested in high-value targets, including early ToolShell exploitation assessed as Chinese-nexus activity against North American government organizations. Identity-centric intrusion methods were also prominent, such as AiTM-enabled credential theft in targeted campaigns against researchers within US think tanks. In Europe, the year combined disruption, espionage, influence operations, and financially motivated intrusions. Across Asia Pacific and Central Asia, Chinese-nexus espionage was sustained, frequently relying on updated versions of established attack playbooks.

Throughout the year, the Americas were a focal point for both nation-state activity and high-end cybercrime, with a wide mix of actors targeting government and private-sector organizations alike. The state-sponsored groups in particular seem to reserve some of their most innovative tradecraft for targets in the Americas. Whether through zero-day exploitation, abuse of cloud services, or highly refined phishing operations, attackers appear willing to invest more time and sophisticated efforts for targets in this region. 🔍

ToolShell is an exploit chain targeting on-premises Microsoft SharePoint and enables unauthenticated remote code execution (RCE) on vulnerable servers. It works by abusing weaknesses in how SharePoint handles certain web service/API requests, which allow attackers to reach code execution without needing valid credentials. ToolShell’s involvement in active exploitation efforts has been observed globally. While analyzing in July the broader wave of ToolShell activity, we found a subset of targeted incidents where the exploit chain appears to have been used as a zero-day, before the original patch was available. In each of these limited early exploitation attempts, the targets were government-sector organizations in North America. We attribute the zero-day exploitation activity to Chinese-nexus threat actors. This assessment is based on the supporting infrastructure we observed in this campaign, which includes router-based relay nodes consistent with Operation Relay Box (ORB)-style networks, an approach most frequently seen in intrusions attributed by multiple vendors to Chinese nexus groups. This assessment aligns with Microsoft Threat Intelligence.

Across these threats, novelty more often came from how familiar techniques were combined than from entirely new tooling. Actors repeatedly used trusted platforms and common enterprise pathways: cloud hosting for command and control, remote administration tooling, DLL side-loading chains, and social engineering patterns such as ClickFix, to reduce detection and improve reliability. 

To read the complete article see: [Read full article](https://research.checkpoint.com/2026/2025-the-untold-stories-of-check-point-research/)