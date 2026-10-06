---
title: Rejetto HFS Servers Actively Scanned for Critical RCE Flaw
date: 2026-10-05
categories: [SECURITY]
tags: [REJETTO,RCE,VULNERABILITY,CYBERSECURITY]
---

## Rejetto HFS Servers Actively Scanned for Critical RCE Flaw 🚨

Hackers are actively scanning for a Rejetto HFS weak signing key vulnerability, tracked as **CVE-2026-61500**, that allows session forgery, account takeover, and remote code execution (RCE). VulnCheck VP of Security Research Caitlin Condon posted on LinkedIn over the weekend that the company's Canary Intelligence honeypots had observed probes targeting CVE-2026-61500. Condon said the observed activity appears to be small-scale reconnaissance from a single China Telecom IP address probing deployments in Japan and the United States.

Rejetto HFS (HTTP File Server) is a free and open-source file-sharing server tool used for self-hosted file sharing on Windows, Linux, and macOS. CVE-2026-61500, first published on July 13, 2026, is a session-cookie signing weakness and leakage issue fixed in Rejetto HFS version 3.2.1. **"Rejetto HFS 3.0.0 through 3.2.0 derives its session-cookie signing key from the non-cryptographic Math.random() generator and discloses outputs of the same generator to unauthenticated clients during login,"** reads the flaw description on the NIST NVD.

Horizon3 researchers discovered the flaw using Anthropic's Mythos model, which identified both the weak signing-key generation and the leak that enabled key recovery. Horizon3 published more details about the flaw and a proof-of-concept (PoC) exploit in a write-up on September 30, 2026.

A remote attacker can collect a small number of login responses, reconstruct the generator's state, recover the signing key, and forge a valid administrator session cookie, leading to full administrative access and remote code execution via the server_code configuration feature. **"Mythos didn't just flag the insecure PRNG in isolation - it simultaneously identified that the application leaked raw Math.random() outputs through a separate code path, recognized those two facts as a chain, and determined the leak produced exactly the observations needed to make state recovery feasible,"** explained Horizon3. The researchers' exploit demonstrates the chain to abuse HFS's built-in ability to execute custom server-side JavaScript to achieve remote code execution.

The release of these technical details may have prompted the probing activity targeting CVE-2026-61500. Possible attack scenarios include accessing, stealing, or deleting HFS files, installing malware on the server, or using the compromised host to access internal systems.

However, VulnCheck has not shared details on successful exploitation or any post-exploitation activity. Users of Rejetto HFS are recommended to upgrade to version 3.2.1 or, ideally, the latest stable release, 3.3.4, as soon as possible.

[Read full article](https://www.bleepingcomputer.com/news/security/rejetto-hfs-servers-now-actively-scanned-for-critical-rce-flaw/)\n