---
title: Progress Patches Critical MOVEit Automation Bug Enabling Authentication Bypass
date: 2026-05-04
categories: [SECURITY]
tags: [PROGRESS,MOVEIT,AUTOMATION,SECURITY,VULNERABILITIES]
---

## Progress Software Addresses Critical MOVEit Automation Bug 🚀

Progress Software has released updates to address two security flaws in MOVEit Automation, including a critical bug that could result in an authentication bypass. MOVEit Automation (formerly Central) is a secure, server-based managed file transfer (MFT) solution used to schedule and automate file movement workflows in enterprise environments without requiring any custom scripts.

The vulnerabilities in question are **CVE-2026-4670** (CVSS score: 9.8), an authentication bypass vulnerability, and **CVE-2026-5174** (CVSS score: 7.7), an improper input validation vulnerability that could allow privilege escalation. Progress Software stated in an advisory that "Critical and high vulnerabilities in MOVEit Automation may allow authentication bypass and privilege escalation through the service backend command port interfaces." Additionally, they noted that "Exploitation may lead to unauthorized access, administrative control, and data exposure."

The shortcomings affect the following versions: MOVEit Automation <= 2025.1.4 (Fixed in MOVEit Automation 2025.1.5), MOVEit Automation <= 2025.0.8 (Fixed in MOVEit Automation 2025.0.9), and MOVEit Automation <= 2024.1.7 (Fixed in MOVEit Automation 2024.1.8). Airbus SecLab researchers Anaïs Gantet, Delphine Gourdou, Quentin Liddell, and Matteo Ricordeau have been credited with discovering and reporting the two vulnerabilities. There are no workarounds that resolve the issues.

While Progress makes no mention of the flaws being exploited in the wild, it is essential that users apply the fixes as soon as possible for optimal protection, particularly given that prior flaws in MOVEit Transfer have been exploited by ransomware gangs like Cl0p.

[Read full article](https://thehackernews.com/2026/05/progress-patches-critical-moveit.html)