---
title: Apt37 Adds New Capabilities for Air Gapped Networks
date: 2026-02-27
categories: [CYBERSECURITY]
tags: [APT37,AIR-GAPPED,MALWARE,CYBERSECURITY]
---

## Apt37 Enhances Its Toolkit for Air Gapped Networks 🚀

In December 2025, Zscaler ThreatLabz uncovered a campaign linked to APT37 (also known as ScarCruft, Ruby Sleet, and Velvet Chollima), a DPRK-backed threat group. This campaign, tracked as **Ruby Jumper** by ThreatLabz, employs Windows shortcut (LNK) files to initiate attacks using a set of newly discovered tools. These tools include **RESTLEAF**, **SNAKEDROPPER**, **THUMBSBD**, and **VIRUSTASK**, which download a payload enabling surveillance on a victim’s system. 

The Ruby Jumper campaign utilizes removable media to infect and relay commands and information between air-gapped systems. Notably, RESTLEAF serves as an initial implant that uses Zoho WorkDrive for C2 communications to fetch additional payloads, such as SNAKEDROPPER. 

### Key Findings 🔍
- **THUMBSBD**: A backdoor that uses removable media to bridge air-gapped network segments, allowing bidirectional command delivery and data exfiltration.
- **FOOTWINE**: A backdoor with surveillance capabilities, including keylogging and audio/video capturing.

APT37 has exploited LNKs as an initial vector for years. In the Ruby Jumper campaign, when a victim opens a malicious LNK file, it launches a PowerShell command that scans the current directory to locate itself based on file size. The PowerShell script carves multiple embedded payloads from fixed offsets within that LNK, including a decoy document and an executable payload. 

### Conclusion 🛡️
This campaign marks a significant evolution in APT37's tactics, showcasing their ability to leverage cloud services like Zoho WorkDrive for malicious purposes. For further details, check out the complete article here: [Read full article](https://www.zscaler.com/blogs/security-research/apt37-adds-new-capabilities-air-gapped-networks)