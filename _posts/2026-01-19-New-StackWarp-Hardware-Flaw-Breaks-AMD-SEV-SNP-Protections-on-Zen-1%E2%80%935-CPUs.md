---
title: New StackWarp Hardware Flaw Breaks AMD SEV-SNP Protections on Zen 1–5 CPUs
date: 2026-01-19
categories: [VULNS]
tags: [AMD,SEV-SNP,HARDWARE FLAW,VULNERABILITY]
---

A team of academics from the CISPA Helmholtz Center for Information Security in Germany has disclosed the details of a new hardware vulnerability affecting AMD processors. The security flaw, codenamed StackWarp, can allow bad actors with privileged control over a host server to run malicious code within confidential virtual machines (CVMs), undermining the integrity guarantees provided by AMD Secure Encrypted Virtualization with Secure Nested Paging (SEV-SNP). It impacts AMD Zen 1 through Zen 5 processors.

Researcher Ruiyi Zhang and colleagues indicated that the flaw enables hijacking both control and data flow, allowing attackers to achieve remote code execution and privilege escalation. AMD has tracked the vulnerability as CVE-2025-29943, classifying it as a medium-severity, improper access control bug.

This vulnerability can be exploited via a previously undocumented control bit on the hypervisor side, allowing manipulation of the stack pointer inside protected VMs, potentially exposing secrets from SEV-secured environments.

The chipmaker released microcode updates for this vulnerability in July and October 2025, with additional patches scheduled for release in April 2026. This finding emphasizes the subtleties of microarchitectural effects undermining system-level security guarantees.

To read the complete article see: [The Hacker News](https://thehackernews.com/2026/01/new-stackwarp-hardware-flaw-breaks-amd.html)