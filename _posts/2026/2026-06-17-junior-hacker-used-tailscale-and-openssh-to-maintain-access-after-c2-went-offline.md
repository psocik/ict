---
title: Junior Hacker Used Tailscale and OpenSSH to Maintain Access After C2 Went Offline
date: 2026-06-17
categories: [CYBERSECURITY]
tags: [HACKER,MALWARE,CYBERSECURITY,TAILSCALE,OPENSSH]
---

## Overview

A **French-speaking attacker** infiltrated a small automotive business in France, deploying a **keylogger** and stealing sensitive banking and email credentials. Before his command-and-control (C2) server went offline, he utilized **OpenSSH** and **Tailscale** on a victim's machine, creating an alternative access point that bypassed the C2 entirely. When the Havoc server went offline the following day, his access remained intact. Eighteen days later, when the C2 returned, his agents reconnected automatically, allowing him to continue his operations.

Cato Networks meticulously documented the entire operation, revealing the attacker's methods after he inadvertently left his SSH keys and a detailed playbook in an open storage bucket. This incident provides a rare glimpse into an intrusion from the operator's perspective rather than just the forensic remnants.

## Attack Details

The actor, known as "Poisson," is not classified as an APT (Advanced Persistent Threat). Researchers describe him as a junior operator, active after 3 p.m. CET, with a long midday break, utilizing free-tier resources. Despite his rudimentary tradecraft, he successfully compromised four machines. The malware primarily operated in memory, employing a **VBScript stager** with a sandbox-evasion delay that decrypted a **PowerShell loader**, which subsequently downloaded a **.NET loader** that executed Havoc's Demon agent without leaving traces on the disk.

Following this, he implemented a scheduled task that executed at every logon with the highest privileges, injected shellcode into **Explorer.exe**, and created a custom-built **RustDesk** as a backup communication channel. The credential grabber was a simple 70-line **Python keylogger** that recorded keystrokes to a local file without any beacon or exfiltration server.

## Key Actions

On **April 7**, during a five-hour overnight session, he installed **OpenSSH Server** and **Tailscale**, connecting the victim's machine to his private Tailscale network and establishing key-based SSH access along with a reverse tunnel. This setup allowed him to access the machine over Tailscale's encrypted mesh without relying on the C2 or exposing any ports. When the C2 infrastructure went offline the next day, his access remained unaffected due to the separate Tailscale network. Upon the C2's return on **April 26**, the agents reconnected automatically without requiring any re-compromise.

The attacker's objectives were narrow, focusing on capturing what users typed: banking logins, email passwords, and government portal credentials. For a small business owner, this represents a significant financial risk. Notably, none of the tools used were new, underscoring the importance of behavior-based detection rather than solely relying on identifying malicious files.

## Recommendations

Cato's recommendations for detection are straightforward:
- **Alert** when OpenSSH Server is installed on a Windows workstation, as this is rarely legitimate.
- Monitor for **tailscale.exe** on machines that have no reason to run a VPN.
- Look for **ssh -R** reverse tunnels connecting to external hosts.
- Additionally, check for **wscript.exe** executing .vbs files from user staging folders, flag scheduled tasks set to the highest privileges that launch script interpreters, and monitor for **powercfg standby-timeout** changes that prevent machines from sleeping.
- Block **DuckDNS**.

The key takeaway: when a C2 is discovered, assume it is not the only entry point. Investigate for any persistent access mechanisms that may remain, as eliminating the C2 while leaving OpenSSH, Tailscale, the scheduled task, and the keylogger intact means the attacker still retains a foothold.

[Read full article](https://thehackernews.com/2026/06/junior-hacker-used-tailscale-and.html)