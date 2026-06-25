---
title: INC Ransomware Targets Mainframes
date: 2026-06-24
categories: [CYBERSECURITY]
tags: [RANSOMWARE,CYBERSECURITY,MALWARE,INC]
---

## INC Ransomware Targets Mainframes 🚀

A recent infrastructure exposure provided a rare look into an active INC ransomware affiliate targeting the Asia-Pacific region. In mid-June 2026, a pair of open directories were identified on AEZA Group LLC, a known bulletproof hosting environment, revealing an operational staging server. The exposed directories contained Windows and Linux encryptors, Group Policy Object (GPO) deployment scripts for a Japanese food and beverage company, and 675 MB of operator tooling, along with exfiltrated victim data.

These findings offered a unique view into an active ransomware campaign in near real-time, revealing undocumented platform targeting, toolchain components, and direct evidence of continued campaigns against large companies in the Asia-Pacific region. One directory exposed a Linux encryptor suite cross-compiled for 14 CPU architectures, including PowerPC, SPARC64, IBM Z (s390x), and RISC-V, not previously linked to INC. INC is actively pivoting toward IBM POWER, SPARC64, and z/Architecture mainframes, platforms that anchor global banking, telecommunications, and high-volume financial transaction processing.

Although the effectiveness of these specific samples remains unverified, their existence shows a calculated effort to disrupt critical networks traditionally isolated from these types of threats.

INC ransomware was first detected in mid-2023, quickly gaining notoriety for its double-extortion campaigns across healthcare, education, and manufacturing sectors. The group claimed nearly 1,000 victims since its inception. In 2024, the source code for both the Windows and Linux/ESXi encryptors was sold on underground forums. The encryptors have since been rewritten in Rust, extending the operating systems targeted.

An open directory included two Windows encryptors and deployment scripts likely linked to a Japanese food and beverage company. The samples communicate with known INC Ransomware infrastructure and its Tor-based companion domain. A second directory hosted 1,853 files, taking up 675 MB, and was used as an active working environment with .ssh, .config, .profile, and .gnupg sitting alongside encryptors, reconnaissance logs, and exfiltrated victim data.

Exfiltrated data from an Asia-Pacific manufacturing company revealed the attacker specifically targeted Active Directory DPAPI backup master keys, which would enable offline decryption of all domain-protected credentials. The exposed directory also contained a full Active Directory enumeration dump, alongside Administrator.ccache, a Kerberos credential cache containing Administrator account tickets, which would enable pass-the-ticket attacks.

Multiple VPN routing scripts establish tunneled access into victim networks. A Python exfiltration script built on the impacket library was recovered. This script, using SMB pass-the-hash with hardcoded Administrator NTLM hashes, targeted a Southeast Asian manufacturer specializing in food production, biotechnology, and chemicals. It prioritized Chrome credential stores and executive desktop contents before moving to HR and sales databases, ERP backups, and related systems.

The expansion of the ransomware's Linux payloads to cover mainframe, POWER, and SPARC64 platforms warrants more attention than the ESXi variants. Operators have established that encrypting a hypervisor is more disruptive than individual endpoints. Targeting these platforms represents a logical escalation, and organizations that have largely remained outside the crosshairs of ransomware groups may now become a primary focus.

[Read full article](https://cyberandramen.net/2026/06/24/inc-ransomware-targets-mainframes-exposed-servers-reveal-cross-platform-payloads-and-apac-campaign/)