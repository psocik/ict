---
title: Public and Private Medical Community Targeted by China-Nexus Threat Actor Pursuing AI and Cyber Research
date: 2026-06-16
categories: [CYBERSECURITY]
tags: [CHINA,CYBERSECURITY,MEDICAL,AI,THREAT-ACTOR]
---

## Overview

The Google Threat Intelligence Group (GTIG) has identified a sophisticated campaign attributed to UNC6508, a People's Republic of China (PRC)-nexus threat actor, targeting institutions in the North American academic, medical, and military research community. This threat actor has remained undetected for over a year, compromising externally facing web applications and deploying bespoke malware for covert data exfiltration. 🚨

### Targeted Entities

The campaign has targeted a diverse set of national, state, and private medical entities, including:
- World-renowned clinical providers
- Premier academic centers
- North American military health institutions
- Professional advocacy groups
- Health regulatory bodies

### Compromise Details

The earliest known compromise occurred in September 2023, where the threat actor exploited externally facing REDCap (Research Electronic Data Capture) servers. REDCap is a web-based software platform designed for managing online databases and surveys in compliance with medical and scientific research regulations. UNC6508 deployed custom malware named **INFINITERED** to capture legitimate REDCap login credentials. After remaining undetected for more than a year, UNC6508 used these credentials to access the victim's internal network. 🔍

### Malware Functionality

Three months after the initial compromise, UNC6508 deployed a custom malware payload tracked as INFINITERED. This malware operates across three distinct modular components:
- **Dropper and Upgrade Interception**
- **Credential Harvester**
- **Backdoor with Command and Control (C2)**

GTIG discovered multiple organizations across the US and Canada compromised with INFINITERED. More than a year after the initial compromise, UNC6508 leveraged overlapping credentials to access an administrator account, using compliance rules to exfiltrate specific email communications. 📧

### Recommendations

GTIG recommends defenders implement the following security measures:
- Enforce phishing-resistant 2-Step Verification (2SV) for enterprise administrator accounts.
- Patch REDCap installations to the latest software version and ensure older versions are completely removed.
- Monitor for INFINITERED using the provided YARA rule and IOCs.
- Audit compliance rules to review Admin audit logs for unauthorized modifications.

For more detailed information, please refer to the full article: [Read full article](https://cloud.google.com/blog/topics/threat-intelligence/prc-targets-us-medical-research)