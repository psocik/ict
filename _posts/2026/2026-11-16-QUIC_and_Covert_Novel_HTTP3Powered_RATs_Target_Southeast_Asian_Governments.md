---
title: QUIC and Covert Novel HTTP/3-Powered RATs Target Southeast Asian Governments
date: 2026-11-16
categories: [CYBERSECURITY]
tags: [CYBERSECURITY,MALWARE,SOUTHEAST ASIA,GOVERNMENT,ESPIONAGE]
---

## QUIC and Covert: Novel HTTP/3-Powered RATs Target Southeast Asian Governments 🚀

Unit 42 has uncovered a multi-stage cyberespionage campaign targeting Southeast Asian government entities since at least July 2025. This activity is tracked as **TGR-STA-0049** (also known as REF7707, Earth Alux, Ink Dragon). The defining signature of the threat actor is the targeting of government entities, utilizing advanced custom payloads designed for high-stealth intelligence collection operations, with a focus on evading security detection tools.

### Key Findings:
- **Previous Activity:** The group previously deployed **Squidoor** (also known as FINALDRAFT), an advanced backdoor used against high-value global targets since 2023.
- **Recent Developments:** The group has expanded its tradecraft, deploying two previously undocumented custom remote access Trojans (RATs): **PerfectPioneer RAT** (spotted in July 2025) and its modular successor, **KUKURAT** (deployed in March 2026).

### Advanced Capabilities:
This campaign features three particularly advanced capabilities:
1. **Covert HTTP/3 (QUIC) C2 communications:** This provides a highly efficient command and control channel that may bypass traditional TCP-optimized deep packet inspection.
2. **Operational Safety Switch:** PerfectPioneer RAT includes a built-in validation engine that actively blocks remote operators from executing noisy or destructive commands that could trigger security alerts.
3. **Multi-Vector Heuristic Camouflage:** KUKURAT employs a custom spoofing engine that generates synthetic, benign-looking network, registry, and file activity.

### Infection Strategy:
The attackers leverage a dual-track infection strategy to establish and maintain a foothold inside targeted organizations through a combination of server exploitation and phishing. The primary infection vector observed is server exploitation, particularly targeting vulnerable, unpatched Microsoft Exchange servers and web servers to deploy web shells. A mix of custom and publicly available web shells, including variations of ASPXSpy, Godzilla, Bysunue.aspx, and Suo5, were utilized.

Phishing tactics serve as a secondary infection vector, using decoy PDFs and lookalike domains to manipulate users into compromising their hosts. This demonstrates a highly targeted strategy designed to maximize deception within high-priority sectors.

### Conclusion:
Both PerfectPioneer RAT and KUKURAT use HTTP/3 as their primary method for communicating with C2 infrastructure. The adoption of HTTP/3 is rare across the broader malware landscape, reflecting an emerging trend among advanced threat actors. This deployment provides a secure and fast communication channel, using the QUIC transport protocol running over UDP, which can bypass traditional security measures.

For more detailed insights, [Read full article](https://unit42.paloaltonetworks.com/custom-rats-target-southeast-asia-governments/).