---
title: BeyondTrust Fixes Critical Pre-Auth Bug Allowing Remote Code Execution
date: 2026-02-09
categories: [SECURITY]
tags: [BEYONDTRUST,SECURITY,VULNERABILITY,REMOTE CODE EXECUTION]
---

## BeyondTrust Security Update 🚨

BeyondTrust has patched a **critical pre-auth flaw** in its Remote Support and Privileged Remote Access (PRA) products that could allow attackers to execute code remotely. This vulnerability, tracked as **CVE-2026-1731** with a CVSS score of **9.9**, enables unauthenticated attackers to send specially crafted requests and run operating system commands without logging in.

### Key Details:
- **Disclosed on:** February 6, 2026
- **Impact:** Full remote code execution if exploited.
- **Affected Versions:** Remote Support versions 25.3.1 and prior, and Privileged Remote Access versions 24.3.4 and prior.

The advisory states, "By sending specially crafted requests, an unauthenticated remote attacker may be able to execute operating system commands in the context of the site user." This flaw poses a significant risk, potentially leading to unauthorized access, data exfiltration, and service disruption.

### Recommendations:
- **SaaS Customers:** Automatically protected as the fix was deployed on February 2, 2026.
- **Self-Hosted Deployments:** Administrators must manually install the patch if automatic updates are not enabled. For PRA self-hosted customers, upgrading to version 25.1.1 or later is essential.

Approximately **11,000 BeyondTrust Remote Support instances** are exposed online, with around **8,500** of these being on-prem systems that could remain vulnerable if not patched. The affected deployments are primarily used by large organizations in sectors such as healthcare, financial services, government, and hospitality.

### Action Required:
We strongly recommend addressing this vulnerability promptly, as exploitation is straightforward. For more details, please read the full advisory.

[Read full article](https://securityaffairs.com/187776/security/beyondtrust-fixes-critical-pre-auth-bug-allowing-remote-code-execution.html)