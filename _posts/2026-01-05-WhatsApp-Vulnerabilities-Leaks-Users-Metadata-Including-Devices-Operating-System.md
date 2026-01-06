---
title: WhatsApp Vulnerabilities Leaks User’s Metadata Including Device’s Operating System
date: 2026-01-05
categories: [CYBER SECURITY]
tags: [WHATSAPP,METADATA,CYBER SECURITY,VULNERABILITIES,PRIVACY]
---

WhatsApp’s multi-device encryption protocol has long leaked metadata, allowing attackers to fingerprint users’ device operating systems, aiding targeted malware delivery. Recent research highlights partial fixes by Meta, but transparency issues persist. Meta’s WhatsApp, with over 3 billion monthly active users, uses end-to-end encryption (E2EE) for message security; however, its multi-device feature reveals device information. In this setup, senders establish separate sessions with each recipient device, using unique encryption keys generated on the device rather than on servers.

Implementation differences in key IDs, like Signed Pre-Key (Signed PK) and One-Time Pre-Key (OTPK), reveal whether a device runs Android or iOS, which is crucial for reconnaissance in cyber kill chains. Attackers exploit this passively by querying WhatsApp servers for session keys without user interaction, identifying OS types to deploy precise exploits and Android malware to Android devices, avoiding iOS or alerting victims. Early 2024 research by Tal A. Be’ery at WOOT’24 exposed leaks of device count, types, and identities via per-device sessions based on Signal’s protocol. In 2025, Gabriel Karl Gegenhuber et al. at WOOT’25 detailed OS fingerprinting: Android Signed PK IDs increment slowly from 0 monthly, while iOS patterns differ sharply. Tal A. Be’ery verified this with custom tools, confirming attackers chain these leaks: detect OS, deliver OS-specific payloads undetected.

Recently, WhatsApp changed the assignment of Android Signed PK IDs to random values across the 24-bit range, thwarting that vector. This change, detected via monitoring tools, marks a shift from Meta’s prior stance, which dismissed it as non-actionable. However, OTPK remains distinguishable: iOS starts low and increments every few days, versus Android’s full random span. Tools adapted post-fix still reliably detect the OS. This enables advanced persistent threats (APTs) to use WhatsApp as a vector for malware, as seen in the Paragon spyware cases. No user notifications occur during queries, thereby preserving stealth.

Critics note that the rollout lacked researcher alerts, bug bounties, or CVE assignment, unlike a similar issue in which a bounty was paid without a CVE. CVEs document issues via CVSS scores, not shame; such omissions hinder tracking. While fixes evolve, full randomization across platforms and CVE transparency would better protect billions, enabling community collaboration. Users should limit linked devices and monitor activity amid ongoing risks.

To read the complete article see: [Cybersecurity News](https://cybersecuritynews.com/whatsapp-device-fingerprinting/) 

*Note: Ensure to follow privacy precautions and manage your device settings accordingly.*