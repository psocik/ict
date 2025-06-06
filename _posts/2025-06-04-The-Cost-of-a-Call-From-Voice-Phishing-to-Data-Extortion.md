---
title: The Cost of a Call From Voice Phishing to Data Extortion
date: 2025-06-04
categories: [APT]
tags: [VOICE PHISHING,DATA EXTORTION,THREAT INTELLIGENCE]
---

Google Threat Intelligence Group (GTIG) is tracking UNC6040, a financially motivated threat cluster that specializes in voice phishing (vishing) campaigns specifically designed to compromise organizations' Salesforce instances for large-scale data theft and subsequent extortion. Over the past several months, UNC6040 has demonstrated repeated success in breaching networks by having its operators impersonate IT support personnel in convincing telephone-based social engineering engagements. This approach has proven particularly effective in tricking employees, often within English-speaking branches of multinational corporations, into actions that grant the attackers access or lead to the sharing of sensitive credentials, ultimately facilitating the theft of organization’s Salesforce data. In all observed cases, attackers relied on manipulating end users, not exploiting any vulnerability inherent to Salesforce.

A prevalent tactic in UNC6040's operations involves deceiving victims into authorizing a malicious connected app to their organization's Salesforce portal. This application is often a modified version of Salesforce’s Data Loader, not authorized by Salesforce. During a vishing call, the actor guides the victim to visit Salesforce's connected app setup page to approve a version of the Data Loader app with a name or branding that differs from the legitimate version. This step inadvertently grants UNC6040 significant capabilities to access, query, and exfiltrate sensitive information directly from the compromised Salesforce customer environments. This methodology of abusing Data Loader functionalities via malicious connected apps is consistent with recent observations detailed by Salesforce in their guidance on protecting Salesforce environments from such threats.

In some instances, extortion activities haven't been observed until several months after the initial UNC6040 intrusion activity, which could suggest that UNC6040 has partnered with a second threat actor that monetizes access to the stolen data. During these extortion attempts, the actor has claimed affiliation with the well-known hacking group ShinyHunters, likely as a method to increase pressure on their victims.

To read the complete article see: [full article](https://cloud.google.com/blog/topics/threat-intelligence/voice-phishing-data-extortion)  

**Source:** Google