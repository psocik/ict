---
title: Shattering the Dream Operation Dream Job Exposed
date: 2026-08-11
categories: [CYBERSECURITY]
tags: [OPERATION DREAM JOB,CYBERSECURITY,LAZARUS GROUP,PHISHING,ZERO-DAY ATTACK]
---

## Shattering the Dream: Operation Dream Job Exposed

Check Point Research is tracking a long-running campaign called **Operation Dream Job**, targeting organizations worldwide, with a particular focus on the defense sector. This campaign is affiliated with the DPRK-linked **Lazarus group**, and its latest wave focuses on the defense sector in Europe and India. Since early 2026, Check Point Research has tracked a wave of the Operation Dream Job campaign, primarily targeting the defense sector worldwide, with a particular emphasis on companies operating in the aerospace and aviation industries.

The Operation Dream Job campaign begins with targeted spear-phishing lures centered on attractive job opportunities at well-known companies in the defense, aerospace, and aviation industries. 🚀

In the latest variant of the Operation Dream Job campaign, the threat actor distributed **SecurityPDF**, a modified PDF viewer designed to open attacker-crafted PDF documents and execute a new backdoor named **Troy**. We observed the threat actor distributing modified PDF viewers designed to execute malicious payloads embedded within specially crafted PDF files, opened by the user. This campaign expanded its delivery method by leveraging impersonation websites and search engine optimization (SEO) techniques to distribute the trojanized applications, increasing its credibility and helping it evade some phishing-based detections.

During the operation, the threat actor deployed a new version of the **FudModule rootkit**, exploiting a zero-day local privilege escalation (LPE) vulnerability in the Windows **AFD.sys** driver to obtain SYSTEM privileges and disable EDR visibility. Following responsible disclosure, Microsoft assigned the vulnerability **CVE-2026-68820** and released a patch on August 11, 2026, as part of their August Patch Tuesday updates. 🔒

Lazarus also used **CVE-2025-49113** to exploit vulnerable Roundcube webmail servers. The attackers' command-and-control infrastructure consists of compromised Roundcube and WordPress servers hosting **RelayShell**, a new PHP webshell that repurposes compromised web servers as relay nodes. At least in one case, a compromised organization in Western Europe was leveraged to conduct a spear-phishing campaign, allowing the attackers to abuse the organization's reputation and trust to target additional victims.

For more detailed insights, check out the full article here: [Read full article](https://research.checkpoint.com/2026/shattering-the-dream-when-a-job-offer-becomes-a-zero-day-attack/)