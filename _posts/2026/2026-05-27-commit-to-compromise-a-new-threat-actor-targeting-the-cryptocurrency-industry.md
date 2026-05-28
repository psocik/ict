---
title: Commit to Compromise A New Threat Actor Targeting the Cryptocurrency Industry
date: 2026-05-27
categories: [CYBERSECURITY]
tags: [CRYPTOCURRENCY,THREAT ACTOR,MALWARE,CYBER ATTACK]
---

## Commit to Compromise: A New Threat Actor Targeting the Cryptocurrency Industry

The Wiz Customer Incident Response Team (CIRT) has investigated multiple intrusions targeting cryptocurrency organizations. These campaigns leveraged sophisticated social engineering techniques, custom macOS malware, and deep targeting of CI/CD infrastructure. The methods used enabled the threat actor to move laterally from compromised employee laptops to code distribution systems and development infrastructure. The Wiz Research team has identified the actor behind these attacks as **JINX-0164**, a previously unreported actor that Wiz is now tracking. This actor has been active since at least mid-2025 and appears to be motivated by financial gain. Their operations targeted developers through recruitment-themed and other social engineering techniques aiming to steal cryptocurrencies, and, in at least one case, conduct a supply chain attack. 🚀

The attack unfolded over a two-week period and followed these key steps:
- **Social Engineering for Initial Access:** The threat actor used a credible LinkedIn profile to contact the victim and offer a virtual meeting.
- **Malware Distribution:** The meeting invite linked to a malicious domain, masquerading as a teleconference provider. Upon clicking, the victim unknowingly downloaded and executed a macOS-specific malware with remote access tool (RAT) capabilities.
- **Credential Access:** The malware was then used to steal credentials from the compromised endpoint.
- **Lateral Movement:** These stolen credentials were leveraged to access internal code distribution systems and development infrastructure.
- **Impact:** Internal source code was modified in an attempt to compromise additional endpoints, most likely to steal cryptocurrency wallet credentials. Throughout the attack, the threat actor masked their cloud activity by routing their connections through VPN services, specifically Mullvad VPN, Astrill VPN, and Express VPN.

The threat actor made initial contact via LinkedIn, impersonating a potential business partner. The LinkedIn profile appeared credible, with established connections, relevant employment history, and industry alignment, making the outreach convincing. The invitation included a link to a malicious domain disguised as a legitimate conferencing platform, such as Microsoft Teams. After clicking the embedded link and executing the program, the victim received **AUDIOFIX**, a Python-based macOS infostealer, via a bash script hosted on a fake driver store domain (apple.driver-store.com). The script downloaded an architecture-aware payload from the same domain, compatible with both Intel and Apple Silicon systems. This payload masquerades as a system audio driver named **coreaudiod**, was saved as **ChromeUpdater**, and was executed via launchctl. The variant observed in this incident communicated with its C2 over HTTPS. The presence of an XOR-encoded password in ~/.zsh_cache on compromised endpoints indicates that AUDIOFIX's password phishing capability was used.

To read the complete article see: [Read full article](https://www.wiz.io/blog/threat-actors-target-crypto-orgs)