---
title: Volt Typhoon Hides Zero-Day Attacks Using 'Silent Train' Framework
date: 2026-10-28
categories: [SECURITY]
tags: [VOLT TYPHOON,ZERO-DAY,SILENT TRAIN,CYBERSECURITY,HACKING]
---

## Volt Typhoon Hides Zero-Day Attacks Using 'Silent Train' Framework 🚀

Chinese state-sponsored hacking group **Volt Typhoon** has been utilizing a sophisticated framework known as **Silent Train** to conduct zero-day attacks on high-value systems. This framework operates through rotating chains of compromised devices, allowing the threat actor to target select systems while maintaining a low profile.

### Key Insights:
- **Targeted Sectors:** The attacks primarily focus on telecommunication firms, government agencies, defense contractors, educational institutions, utilities, and critical infrastructure.
- **Geographical Focus:** The most targeted regions include California, Texas, and Hawaii, indicating a strategic interest in Indo-Pacific matters.
- **Historical Context:** Volt Typhoon has previously targeted U.S. critical infrastructure, including communications and energy sectors, with warnings from CISA about potential disruptions during crises.

### Technical Overview:
Silent Train functions as a relay infrastructure, masking the origin of attacks by routing activities through compromised devices and VPS infrastructure outside the U.S. Notably, Intelbras modems and Netgear Orbi devices have been identified as key components in this relay system.

### Exploited Vulnerabilities:
Researchers have tracked multiple zero-day exploits associated with Silent Train, including vulnerabilities in:
- **CVE-2026-16812** - VeloCloud Orchestrator
- **CVE-2026-20127** - Cisco Catalyst SD-WAN
- **CVE-2025-8875** and **CVE-2025-8876** - N-able N-central
- **CVE-2024-39717** - Versa Director
- **Quest KACE** (suspected zero-day)

### Recommendations:
To mitigate risks, Black Lotus Labs suggests:
- Strengthening security around centralized management systems.
- Restricting internet access to administrative interfaces.
- Rapidly patching vulnerabilities.
- Centralizing logs with longer retention periods.
- Monitoring for unusual administrative activities.

For more detailed information, you can read the full article here: [Read full article](https://www.bleepingcomputer.com/news/security/volt-typhoon-hides-zero-day-attacks-using-silent-train-framework/)