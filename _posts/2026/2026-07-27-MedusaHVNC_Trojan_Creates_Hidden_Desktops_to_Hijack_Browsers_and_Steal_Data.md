---
title: MedusaHVNC Trojan Creates Hidden Desktops to Hijack Browsers and Steal Data
date: 2026-07-27
categories: [MALWARE]
tags: [MEDUSAHVNC,TROJAN,MALWARE,DATA-THEFT]
---

## MedusaHVNC Trojan: A New Threat to Your Data 🚨

The **MedusaHVNC RAT** is a sophisticated remote access trojan that utilizes hidden Windows desktops to remotely control browsers, steal data, and evade detection through legitimate system features. Recently, BlackFog's research team dissected this new malware, revealing alarming capabilities.

### Key Features of MedusaHVNC:
- **Hidden Virtual Desktops:** Operates on a separate Windows desktop, out of sight of the victim.
- **Browser Control:** Accesses live, logged-in sessions while the activity appears to come from the victim's usual machine.
- **Wide Compatibility:** Supports major browsers like Chrome, Edge, Brave, Firefox, and even Telegram.

### Infection Chain:
The infection process involves five stages, starting with a JScript launcher that executes an obfuscated script. This script pauses for 7,584 milliseconds before dropping various malicious components into the Temp directory. The process includes:
- **AutoIt Interpreter:** Decrypts the payload using a single-byte XOR key.
- **Malicious Executable:** An unsigned 64-bit executable that communicates with its operator through a custom protocol.

### Conclusion:
BlackFog emphasizes that this malware cannot hide from network monitoring. Blocking connections to known command and control infrastructure is crucial to mitigate the threat.

For more detailed insights, check out the full article here: [Read full article](https://securityaffairs.com/196111/malware/medusahvnc-trojan-creates-hidden-desktops-to-hijack-browsers-and-steal-data.html)