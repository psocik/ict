---
title: CrackArmor - Critical AppArmor Flaws Enable Local Privilege Escalation to Root
date: 2026-03-13
categories: [SECURITY]
tags: [APPARMOR,VULNERABILITIES,SECURITY,LINUX]
---

## CrackArmor - Critical AppArmor Flaws Enable Local Privilege Escalation to Root

🚨 **Qualys TRU** has discovered critical vulnerabilities in AppArmor, dubbed **"CrackArmor"**, that allow unprivileged users to bypass kernel protections and escalate privileges to root. This flaw has been present since 2017 and affects over **12.6 million systems** globally.

### Key Findings
- **Confused Deputy Vulnerabilities**: These vulnerabilities allow unprivileged users to manipulate security profiles, bypass user-namespace restrictions, and execute arbitrary code within the kernel.
- **Local Privilege Escalation**: Attackers can exploit these flaws to escalate privileges to root, potentially leading to denial-of-service attacks and kernel panics.

### Impact
The vulnerabilities expose critical gaps in security assumptions and undermine system confidentiality, integrity, and availability. The flaws are present in all Linux kernels since v4.11 across distributions that integrate AppArmor, including Ubuntu, Debian, and SUSE.

### Recommendations
Organizations should treat this advisory as a priority patching event. Immediate kernel patching is essential to neutralize these vulnerabilities. Ensure to:
- Apply vendor kernel updates immediately.
- Scan for exposure.
- Monitor for unauthorized profile modifications.

Don't underestimate the significance of these vulnerabilities due to the absence of CVE identifiers. If you are running affected versions, take action now to secure your systems! 🔒

For more details, [Read full article](https://blog.qualys.com/vulnerabilities-threat-research/2026/03/12/crackarmor-critical-apparmor-flaws-enable-local-privilege-escalation-to-root)