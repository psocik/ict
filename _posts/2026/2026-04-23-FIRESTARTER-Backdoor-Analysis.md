---
title: FIRESTARTER Backdoor Analysis
date: 2026-04-23
categories: [CYBERSECURITY]
tags: [MALWARE,CYBERSECURITY,CISA,APT]
---

## FIRESTARTER Backdoor Analysis 🚨

The Cybersecurity and Infrastructure Security Agency (CISA) has conducted an in-depth analysis of the FIRESTARTER malware, which was obtained during a forensic investigation. CISA, along with the United Kingdom National Cyber Security Centre (NCSC), has determined that advanced persistent threat (APT) actors are utilizing FIRESTARTER malware to maintain persistence, specifically targeting publicly accessible Cisco Firepower and Secure Firewall devices that are running Adaptive Security Appliance (ASA) or Firepower Threat Defense (FTD) software.

CISA and NCSC have released a Malware Analysis Report to share their findings regarding a FIRESTARTER malware sample that operates as a backdoor. They urge organizations to take immediate response actions. Notably, CISA has observed successful implantations of this malware in the wild on Cisco Firepower devices running ASA software.

### Key Findings 🔍
- **FIRESTARTER** is a backdoor that allows remote access and control, forming part of a broader campaign that grants APT actors initial access to Cisco ASA firmware by exploiting vulnerabilities such as CVE-2025-20333 and CVE-2025-20362.
- This malware can persist as an active threat on Cisco devices, maintaining access even after patches are applied, as it is not removed by firmware updates.
- APT actors initially deployed LINE VIPER as a post-exploitation implant and subsequently used FIRESTARTER to ensure continued access to the compromised device.

### Technical Details 💻
FIRESTARTER is a Linux Executable and Linkable File (ELF) designed to execute on Cisco Firepower and Secure Firewall devices. It establishes a command and control (C2) channel for remote access and control. The malware achieves persistence by detecting termination signals and relaunching itself, surviving firmware updates and device reboots unless a hard power cycle occurs.

CISA and NCSC recommend that U.S. and U.K. organizations utilize YARA rules to detect FIRESTARTER malware against disk images or core dumps of affected devices and report any findings to CISA or NCSC. If a compromise is confirmed, organizations should conduct incident response actions.

For further details, please refer to the full article: [Read full article](https://www.cisa.gov/news-events/analysis-reports/ar26-113a)