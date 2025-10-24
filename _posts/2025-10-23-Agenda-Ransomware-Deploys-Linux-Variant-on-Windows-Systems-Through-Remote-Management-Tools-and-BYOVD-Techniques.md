---
title: Agenda Ransomware Deploys Linux Variant on Windows Systems Through Remote Management Tools and BYOVD Techniques
date: 2025-10-23
categories: [MALWARE]
tags: [RANSOMWARE,LINUX,WINDOWS,CYBERSECURITY,REMOTE ACCESS]
---

Trend Research has identified a sophisticated Agenda ransomware attack, also known as Qilin, deploying a Linux-based ransomware binary on Windows systems, bypassing traditional Windows-centric security measures. The group has been active since January 2025, affecting 591 victims across 58 countries, primarily targeting organizations in developed markets and high-value industries, like manufacturing, technology, financial services, and healthcare. The cross-platform execution makes detection challenging.

The attack utilizes a novel deployment method combining WinSCP for secure file transfer and Splashtop Remote for executing the Linux ransomware on Windows. Attackers also installed AnyDesk through ATERA Networks’ remote monitoring and management (RMM) platform and ScreenConnect for command execution. This allows for low-noise operations, disabling recovery options through targeted theft of backup credentials and neutralizing endpoint defenses via BYOVD attacks. The attackers strategically deploy multiple SOCKS proxy instances across various system directories to obfuscate command-and-control traffic.

This attack challenges traditional Windows-focused security controls. The strategic targeting of Veeam backup infrastructure using specialized credential extraction tools harvests credentials from multiple backup databases, compromising the organization’s disaster recovery capabilities. This, combined with BYOVD techniques and fake CAPTCHA social engineering, ensures successful ransomware deployment while eliminating recovery options.

The initial attack vector involves fake CAPTCHA pages hosted on Cloudflare R2 storage. Delivering information stealers to harvest authentication tokens, browser cookies, and stored credentials. A SOCKS proxy DLL is loaded into memory via rundll32.exe to facilitate remote access and command execution. A backdoor administrative account named Supportt is created for persistent elevated access, and legitimate administrator account passwords are reset.

Organizations using remote access platforms, centralized backup solutions, or hybrid Windows/Linux infrastructures are at risk. Mitigation includes limiting remote access tool use to authorized hosts and continuously monitoring for unusual activity. Reconnaissance is conducted using tools like NetScan and commands like nltest /domain_trusts and net group "domain admins" /domain via ScreenConnect. PowerShell scripts with base64-encoded payloads target Veeam backup databases, extracting credentials for domain administrator accounts, service accounts, and local administrators.