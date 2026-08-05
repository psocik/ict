---
title: New XCSSET Variant Targets macOS Developers via Compromised Xcode Projects
date: 2026-08-04
categories: [SECURITY]
tags: [XCSSET,MALWARE,MACOS,XCODE,SECURITY]
---

## New XCSSET Variant Targets macOS Developers 🚨

A new version of the **XCSSET malware** is targeting thousands of macOS users through compromised Xcode projects and GitHub repositories. Xcode is the official software development kit (SDK) for creating, testing, and publishing software for all of Apple's platforms. After months of inactivity, XCSSET has resurfaced with an updated version, v40, that features enhanced evasion techniques and introduces two new components, researchers have found.

Researchers at Palo Alto Networks' Unit 42, who analyzed the infection chain, say the threat actor spreads the malware by compromising vulnerable Git repositories and injecting a downloader script into benign files within Xcode projects. Developers downloading the compromised projects become infected upon building them, allowing XCSSET to compromise every other Xcode project on the system and propagate further through shared source code.

Unit 42 researchers observed XCSSET version 40 used in two distinct attack waves in mid-April and early May. XCSSET has targeted macOS systems since at least 2021 and has, in some cases, exploited zero-day vulnerabilities in its attacks. In September 2025, Microsoft warned of an XCSSET campaign that used compromised Xcode projects as a distribution mechanism.

### Infection Chain and New Modules 🔗

In the attacks analyzed by Unit 42, XCSSET follows a four-stage infection chain before deploying 17 separate modules that enable credential theft, keystroke logging, clipboard manipulation, browser hijacking, and data exfiltration. The newest XCSSET version features two new modules, namely a **Chrome hijacker** and a **Telegram trojanizer**. The hijacker wraps the Chrome browser in a malicious launcher and enables the Chrome DevTools Protocol (CDP) on a local port to fetch JavaScript from the attacker's command-and-control (C2) infrastructure. This code allows the attackers to intercept web traffic, including credentials, cookies, and MetaMask transactions, which can be manipulated on the fly to divert payments.

Additionally, the hijacker module enables system command execution via a fileless reverse shell, which Google blocks in Chrome for Windows and is currently working to extend these protections to macOS. The Telegram trojanizer deletes the legitimate Telegram Desktop application on infected systems and replaces it with a malicious version, potentially used for intercepting victims' communications. Unit 42 could not retrieve its encrypted configuration; hence, its exact functionality remains unknown.

### Evasion Measures and Recommendations 🛡️

The researchers also highlighted XCSSET's new detection-evasion measures, including periodically re-compiling the loader on the C2 server, using separate encryption keys for inbound and outbound communications, and obfuscating function names, variables, and strings, with build-unique ciphers. The malware aggressively attempts to disable macOS security such as XProtect, MRT, TCC, and Rapid Security Response, terminates Apple's CloudTelemetryService, and prevents XProtect signature updates.

Unit 42 recommends monitoring for anomalous AppleScript activity, unauthorized browser modifications, suspicious macOS defaults domains, and ad hoc-signed applications that bypass Gatekeeper. To defend against the latest version of XCSSET, the researchers also recommend scanning open-source dependencies to prevent compromised repositories from entering software development pipelines.

For more details, check out the full article: [Read full article](https://www.bleepingcomputer.com/news/security/new-xcsset-variant-targets-macos-devs-via-compromised-xcode-projects/)