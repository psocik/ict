---
title: Operation CameraSwarm Over 14,000 Dahua Cameras Compromised Across Ukraine and Russia
date: 2026-08-18
categories: [CYBERSECURITY]
tags: [DAHUA,MALWARE,CAMERAS,CYBERSECURITY,UKRAINE,RUSSIA]
---

## Operation CameraSwarm: Over 14,000 Dahua Cameras Compromised Across Ukraine and Russia

🚨 Between **17 June and 22 July 2026**, a single operator compromised over **14,000 Dahua IP cameras**. The scanning behind it was global, starting with masscan sweeps against the Russian address space and then expanding across the full IPv4 range. The confirmed, geolocated compromises were concentrated in **Ukraine and Russia**, with Ukraine holding the largest share.

This marks the second Dahua-related camera compromise operation traced back to an exposed operator directory in just two weeks. On **23 July**, Hunt.io AttackCapture crawled the operator's own server and recovered their entire working environment, totaling **2,616 files across 234 subdirectories** and **407 MB** from an open HTTP directory they had exposed.

### Key Findings:
- The operation resulted in **14,530+ devices compromised** in just **35 days**.
- A brute-force engine reached **12,324 unique addresses**.
- **1,923 cameras** were found to carry a persistent backdoor account (p2pwn / p2password), installed over RPC after either bypass. This backdoor survives password changes and, on most firmware, even factory resets.
- **283 cameras** were accessed solely by serial number through Dahua's cloud relay, often without device addresses or credentials.

The operator's code indicates that **89.4%** of live serials required no authentication, and offline recovery codes grant cloud-level administrative access by serial number, independent of device credentials. This design strongly suggests that the toolkit was built to provide access to a third party.

Additionally, a separate capability was staged on the same host: a **UPX-packed Windows binary** classified as **SalatStealer**, complete with a five-method Defender bypass script. The toolkit is assembled from components credited to at least six upstream developers.

It is important to note that two CVE identifiers used throughout the operator's tooling do not survive verification, although the techniques themselves are real. For instance, CVE-2024-39943 is incorrectly labeled as a persistent-backdoor technique, while CVE-2025-31702 describes a post-authentication privilege escalation that does not align with the unauthenticated relay abuse documented by researchers.

For more details, check out the full article: [Read full article](https://hunt.io/blog/operation-cameraswarm-dahua-cameras-compromised)