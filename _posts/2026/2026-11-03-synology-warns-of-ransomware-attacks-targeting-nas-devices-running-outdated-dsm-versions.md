---
title: Synology Warns of Ransomware Attacks Targeting NAS Devices Running Outdated DSM Versions
date: 2026-11-03
categories: [SECURITY]
tags: [SYNOLOGY,RANSOMWARE,NAS,SECURITY,UPDATE]
---

## Synology Warns of Ransomware Attacks

Synology has issued a warning regarding ransomware attacks that are exploiting a flaw in outdated NAS devices. Users are urged to update their DiskStation Manager (DSM) immediately! 🚨

A security fix released in 2024 is now at the center of these ransomware attacks. The company has discovered that attackers are targeting systems running outdated versions of DSM, putting files stored on these network storage devices at risk of encryption and extortion. Synology disclosed these attacks on October 29, 2026, revealing that threat actors are taking advantage of a vulnerability that was addressed back in December 2024. 

> "These attacks aim to encrypt data and extort ransom." 💰

The company refers customers to Synology-SA-24:20, a security advisory published on November 5, 2024, which documents three flaws affecting DSM. The advisory has been updated as fixes became available across different software branches, with the DSM 6.2 update released on December 5. 

### Vulnerabilities Identified
- **CVE-2024-10441**: Most severe with a CVSS score of 9.8, affecting the system plugin daemon, allowing unauthenticated remote attackers to execute arbitrary code.
- **CVE-2024-50629**: CVSS score of 5.3, affecting the DSM webapi component, allowing remote attackers to read limited files.
- **CVE-2024-10445**: Rated 4.3, concerning improper certificate validation in the update functionality, allowing an attacker in an adjacent network position to write limited files.

Synology has not confirmed which of these vulnerabilities attackers are exploiting, so all three should be considered part of the security advisory, not confirmed entry points in the current ransomware campaign.

The vendor has released corrected builds for all affected DSM branches. Users should check the full version number installed on their NAS and compare it with the minimum fixed releases listed in the advisory:
- **DSM 7.2.2**: 7.2.2-72806-1 or later.
- **DSM 7.2.1**: 7.2.1-69057-6 or later.
- **DSM 7.2**: 7.2-64570-4 or later.
- **DSM 7.1**: 7.1.1-42962-7 or later.
- **DSM 6.2**: 6.2.4-25556-8 or later.

The impact of a ransomware infection on a NAS can extend beyond the storage device itself. Businesses often use these systems to keep shared documents, operational files, and backup copies in one place. If attackers encrypt that data, employees may lose access to essential information, making recovery much harder if the NAS also holds the backups needed to restore other systems. 

Updating DSM is therefore an immediate priority for administrators and home users alike. Synology also advises customers to enable automatic updates to ensure future security fixes are applied without manual intervention. 

For more details, check the full article here: [Read full article](https://securityaffairs.com/202343/security/synology-warns-of-ransomware-attacks-targeting-nas-devices-running-outdated-dsm-versions.html) 
