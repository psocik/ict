---
title: Dissecting Sapphire Sleet's macOS Intrusion from Lure to Compromise
date: 2026-06-16
categories: [CYBERSECURITY]
tags: [SAPPHIRE SLEET,MACOS,CYBER ATTACK,NORTH KOREA,MALWARE]
---

## Dissecting Sapphire Sleet's macOS Intrusion from Lure to Compromise

Microsoft has identified an additional **Sapphire Sleet** macOS intrusion that follows the same core attack chain previously documented, but with updated lures, infrastructure, and component naming. This cyber campaign, orchestrated by the North Korean threat actor **Sapphire Sleet**, relies on social engineering rather than software vulnerabilities. 

### Who is Sapphire Sleet?
Sapphire Sleet is a North Korean state actor active since at least March 2020, primarily targeting the finance sector, including cryptocurrency, venture capital, and blockchain organizations. Their main motivation is to steal cryptocurrency wallets to generate revenue and target technology or intellectual property related to cryptocurrency trading and blockchain platforms. 

### How the Attack Works
By impersonating a legitimate software update, threat actors trick users into manually running malicious files, allowing them to steal passwords, cryptocurrency assets, and personal data while avoiding built-in macOS security checks. 

Microsoft Threat Intelligence identified a campaign beginning in early 2026 by Sapphire Sleet demonstrating new combinations of macOS-focused execution patterns and techniques. They operate a well-documented social engineering playbook, creating fake recruiter profiles on social media and professional networking platforms, directing targets to install malicious software. 

In this observed activity, the target was directed to download a file called **Zoom SDK Update.scpt**—a compiled AppleScript that opens in macOS Script Editor by default. This trusted first-party Apple application can execute arbitrary shell commands, allowing the activity to proceed outside of macOS protections such as Transparency, Consent, and Control (TCC), Gatekeeper, quarantine enforcement, and notarization checks. 

### The Attack Unfolds
When the user opens the **Zoom SDK Update.scpt** file, macOS launches it in Script Editor, allowing Sapphire Sleet to transition from a single lure file to a multi-stage, dynamically fetched payload chain. The entire attack unfolds through a cascading chain of curl commands, each fetching and executing progressively more complex AppleScript payloads. The main payload fetched by the mac-cur1 user agent is the attack orchestrator. 

The malware starts by collecting basic system details and registers the compromised system with its command-and-control (C2) infrastructure. The first binary deployed is a host monitoring component called **com.apple.cli**—a ~5 MB Mach-O binary disguised with an Apple-style naming convention. During execution, **com.apple.cli** performs host reconnaissance while maintaining repeated outbound connectivity to the threat actor-controlled C2 endpoint **83.136.208[.]246:6783**. 

Apple has since implemented updates to help detect and block infrastructure and malware associated with this campaign.

[Read full article](https://www.microsoft.com/en-us/security/blog/2026/04/16/dissecting-sapphire-sleets-macos-intrusion-from-lure-to-compromise/)