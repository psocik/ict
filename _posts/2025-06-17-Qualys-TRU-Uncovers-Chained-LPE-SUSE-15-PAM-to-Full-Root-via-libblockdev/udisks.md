---
title: Qualys TRU Uncovers Chained LPE SUSE 15 PAM to Full Root via libblockdev/udisks
date: 2025-06-17
categories: [VULNERABILITIES]
tags: [QUALYS,LPE,SECURITY,LINUX,VULNERABILITY]
---

The Qualys Threat Research Unit (TRU) has discovered two linked local privilege escalation (LPE) flaws.

The first (CVE-2025-6018) resides in the PAM configuration of openSUSE Leap 15 and SUSE Linux Enterprise 15. Using this vulnerability, an unprivileged local attacker—for example, via SSH—can elevate to the “allow_active” user and invoke polkit actions normally reserved for a physically present user.

The second (CVE-2025-6019) affects libblockdev, is exploitable via the udisks daemon included by default on most Linux distributions, and allows an “allow_active” user to gain full root privileges. Although CVE-2025-6019 on its own requires existing allow_active context, chaining it with CVE-2025-6018 enables a purely unprivileged attacker to achieve full root access.

This libblockdev/udisks flaw is extremely significant. Although it nominally requires “allow_active” privileges, udisks ships by default on almost all Linux distributions, so nearly any system is vulnerable. Techniques to gain “allow_active”, including the PAM issue disclosed here, further negate that barrier. An attacker can chain these vulnerabilities for immediate root compromise with minimal effort. Given the ubiquity of udisks and the simplicity of the exploit, organizations must treat this as a critical, universal risk and deploy patches without delay.

[Read the complete article here.](https://blog.qualys.com/vulnerabilities-threat-research/2025/06/17/qualys-tru-uncovers-chained-lpe-suse-15-pam-to-full-root-via-libblockdev-udisks)