---
title: FIRESTARTER Backdoor Analysis by CISA
date: 2026-04-23
categories: [CYBERSECURITY]
tags: [MALWARE,CYBERSECURITY,CISA,FIRESTARTER]
---

## FIRESTARTER Backdoor Analysis by CISA

The Cybersecurity and Infrastructure Security Agency (CISA) has conducted an analysis of the FIRESTARTER malware, which was obtained from a forensic investigation. CISA, along with the United Kingdom National Cyber Security Centre (NCSC), has determined that advanced persistent threat (APT) actors are utilizing FIRESTARTER malware to maintain persistence, specifically targeting publicly accessible Cisco Firepower and Secure Firewall devices running Adaptive Security Appliance (ASA) or Firepower Threat Defense (FTD) software. 🚨

CISA and the NCSC are releasing this Malware Analysis Report to share insights on a FIRESTARTER malware sample functioning as a backdoor and to urge organizations to implement key response actions. Notably, CISA has only observed a successful implant of this malware in the wild on a Cisco Firepower device running ASA software.

### Key Findings
- **FIRESTARTER** is a backdoor that allows remote access and control, part of a larger campaign that provided APT actors initial access to Cisco ASA firmware by exploiting vulnerabilities CVE-2025-20333 and CVE-2025-20362.
- This malware can persist as an active threat on Cisco devices, maintaining access even after patches are applied, as it is not removed by firmware updates.
- APT actors initially deployed LINE VIPER as a post-exploitation implant and subsequently used FIRESTARTER to ensure continued access to the compromised device.

### Technical Details
FIRESTARTER is a Linux Executable and Linkable File (ELF) designed to operate on Cisco Firepower and Secure Firewall devices. It serves as a command and control (C2) channel for remote access and control. The malware achieves persistence by detecting termination signals and relaunching itself, surviving firmware updates and device reboots unless a hard power cycle occurs. 🔄

CISA and the NCSC recommend that organizations utilize YARA rules to detect FIRESTARTER malware against either a disk image or core dump of a device and report any findings to CISA or the NCSC. If a compromise is confirmed, it is crucial to conduct incident response actions promptly.

For further details, please read the complete article: [Read full article](https://www.cisa.gov/news-events/analysis-reports/ar26-113a)