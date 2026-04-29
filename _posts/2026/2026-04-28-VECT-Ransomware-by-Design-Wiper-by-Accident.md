---
title: VECT Ransomware by Design, Wiper by Accident
date: 2026-04-28
categories: [CYBERSECURITY]
tags: [RANSOMWARE,MALWARE,CYBERSECURITY,CHECK-POINT-RESEARCH]
---

## VECT: Ransomware by Design, Wiper by Accident 🚨

Check Point Research has discovered that the **VECT 2.0 ransomware** permanently destroys large files instead of encrypting them. A critical flaw in the encryption implementation, which is identical across all three platform variants (Windows, Linux, ESXi), discards three of four decryption nonces for every file larger than 131,072 bytes (128 KB). This means full recovery is impossible for anyone, including the attacker! 😱

At a threshold of only 128 KB, this effectively makes VECT a wiper for virtually any file containing meaningful data, including enterprise assets such as VM disks, databases, documents, and backups. CPR confirmed that this flaw is present across all publicly available VECT versions.

### Misidentified Cipher 🔍

The cipher used by VECT has been misidentified in public reporting. VECT employs raw **ChaCha20-IETF (RFC 8439)** with no authentication, not ChaCha20-Poly1305 AEAD as claimed in several widely cited threat intelligence reports. There is no Poly1305 MAC and no integrity protection. Additionally, advertised encryption speed modes are not implemented. The `--fast`, `--medium`, and `--secure` flags present across Linux and ESXi variants are parsed and then silently ignored. Every execution applies identical hardcoded thresholds regardless of operator selection.

### Identical Encryption Design 🔒

Windows, Linux, and ESXi variants share an identical encryption design built on **libsodium**, with the same file-size thresholds, the same four-chunk logic, and the same nonce-handling flaw throughout, confirming a single codebase ported across platforms. Beyond the nonce flaw, CPR identified multiple additional bugs and design failures across all variants, from self-cancelling string obfuscation and permanently unreachable anti-analysis code to a thread scheduler that actively degrades the encryption performance it meant to improve.

### Ransomware-as-a-Service (RaaS) 💼

VECT Ransomware is a Ransomware-as-a-Service (RaaS) program that made its first appearance in December 2025 on a Russian-language cybercrime forum. After claiming their first two victims in January 2026, the group gained public attention due to an announcement of a partnership with **TeamPCP**, the actor behind several supply-chain attacks in March 2026. These attacks injected malware into popular software packages such as Trivy, Checkmarx' KICS, LiteLLM, and Telnyx, affecting a large base of downstream consumers.

Shortly after these attacks made headlines, VECT announced their partnership with TeamPCP on **BreachForums**, aiming to exploit the companies affected by those supply chain attacks. Furthermore, VECT announced a partnership with BreachForums itself, promising that every registered forum user would become an affiliate and thus be able to use the VECT ransomware, negotiation platform, and leak site for operations. As of April 2026, this partnership is in full effect.

[Read full article](https://research.checkpoint.com/2026/vect-ransomware-by-design-wiper-by-accident/)