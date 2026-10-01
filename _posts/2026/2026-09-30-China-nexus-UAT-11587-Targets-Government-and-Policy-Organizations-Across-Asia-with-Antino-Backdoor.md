---
title: China-nexus UAT-11587 Targets Government and Policy Organizations Across Asia with Antino Backdoor
date: 2026-09-30
categories: [CYBERSECURITY]
tags: [CHINA,GOVERNMENT,POLICY,BACKDOOR,SECURITY]
---

## China-nexus UAT-11587 Targets Government and Policy Organizations Across Asia with Antino Backdoor 🚀

Cisco Talos has uncovered a cluster of activity tracked as **UAT-11587**, targeting government and policy organizations across Asia, including Taiwan, India, the Philippines, and Cambodia. This operation delivers a previously undocumented backdoor known as **"Antino"** in developer artifacts. Talos first observed UAT-11587 activity in **September 2025**. By **July 2026**, at least **16** affected or targeted institutional environments across **eight Asian countries** had been identified.

### What is Antino? 🔍
Antino is a **Rust-compiled Windows backdoor** that supports:
- Host reconnaissance
- Shell and PowerShell execution
- File transfer
- In-memory shellcode loading
- Persistence

Its native command-and-control channel operates exclusively through **Microsoft 365**, utilizing Microsoft Graph to interact with Outlook and OneDrive. Talos identified a recurring delivery branch that began with spear-phishing emails and tailored decoy documents, followed by a five-stage infection chain. The actor relied heavily on **Cloudflare infrastructure** for delivery, execution tracking, and payload staging.

### Spear-Phishing Tactics 🎯
UAT-11587, like many targeted intrusion sets, uses spear-phishing emails to deliver its infection chain. The social engineering themes suggest that the threat actor had detailed prior knowledge of their target organizations. To enhance credibility, UAT-11587 spoofed sender identities trusted by the intended recipients, exploiting the distinction between the SMTP envelope sender and the visible From header. Another technique involved closely replicating Gmail's native attachment preview widget within the email HTML body.

### Conclusion 📊
Talos assesses with high confidence that UAT-11587 is a **China-nexus actor**, based on corroborating technical and operational evidence. The campaign's lure theme and targeting align with interests typical of China-nexus actors, focusing on public-sector and national-security-adjacent organizations across Asia. By July 2026, Talos had identified approximately **350 compromised endpoints** across eight countries.

For more details, check out the full article: [Read full article](https://blog.talosintelligence.com/china-nexus-uat-11587-targets-government-and-policy-organizations-across-asia-with-antino-backdoor/) 
