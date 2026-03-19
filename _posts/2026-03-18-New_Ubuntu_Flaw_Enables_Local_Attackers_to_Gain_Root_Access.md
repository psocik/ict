---
title: New Ubuntu Flaw Enables Local Attackers to Gain Root Access
date: 2026-03-18
categories: [SECURITY]
tags: [UBUNTU,VULNERABILITY,SECURITY,ROOT ACCESS]
---

## New Ubuntu Flaw Enables Local Attackers to Gain Root Access 🚨

A newly identified local privilege escalation (LPE) vulnerability has been discovered affecting default installations of Ubuntu Desktop 24.04 and later, allowing attackers to gain full root access. The flaw, tracked as **CVE-2026-3888**, stems from the interaction between two core system components and was uncovered by the **Qualys Threat Research Unit**.

### Key Details:
- **Severity:** High (CVSS score of 7.8)
- **Complexity:** High due to required timing window
- **User Interaction:** None needed, only low-level access required

### How the Attack Works:
The flaw relies on a timing-based attack chain. Attackers exploit automated system cleanup processes to replace critical directories with malicious content. Key elements of the attack include:
- Waiting for temporary file cleanup, which occurs after 10-30 days, depending on the system version.
- Recreating a deleted directory with malicious payloads.
- Triggering snap-confine to execute these files with root privileges.

### Affected Systems:
The vulnerability impacts multiple Ubuntu releases, particularly those using snapd package versions before recent updates. Users and organizations are advised to upgrade immediately to patched versions:
- **Ubuntu 24.04 LTS** to snapd 2.73+ubuntu24.04.2 or later
- **Ubuntu 25.10 LTS** to snapd 2.73+ubuntu25.10.1 or later
- **Ubuntu 26.04 (development)** to snapd 2.74.1+ubuntu26.04.1 or later
- **Upstream snapd** to version 2.75 or later

Legacy systems are not affected by default configurations but may still benefit from applying patches as a precaution.

Additionally, during a separate review ahead of Ubuntu 25.10's release, Qualys identified another flaw in the uutils coreutils package. This issue involved a race condition in the rm utility that could allow attackers to manipulate file deletions during scheduled system tasks. The vulnerability was addressed before public release.

For more information, [Read full article](https://www.infosecurity-magazine.com/news/ubuntu-flaw-enables-root-access/)