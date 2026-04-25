---
title: New WireTap Attack Breaks Server SGX to Exfiltrate Sensitive Data
date: 2025-10-05
categories: [CYBER SECURITY]
tags: [VULNERABILITY,WIRETAP ATTACK,SGX,INTELLIGENCE]
---

A newly disclosed vulnerability, named the WireTap attack, allows attackers with physical access to break the security of Intel’s Software Guard eXtensions (SGX) on modern server processors and steal sensitive information.

The core of the WireTap attack is a custom-built memory interposition probe that physically taps into the DRAM bus, allowing the attacker to observe the data moving between the CPU and the system’s memory. A key innovation was slowing down the system’s high-speed DDR4 memory bus. By modifying the DIMM’s metadata, the researchers forced the system to operate at a much lower frequency. This crucial step made it possible to capture the data traffic using outdated and inexpensive logic analyzers not originally designed for modern hardware. This approach shatters the long-held assumption that physical memory attacks on server-grade systems were out of reach for all but the most well-funded adversaries.

The attack specifically targets Scalable SGX, the version used in Intel’s Xeon server processors, which relies on a deterministic memory encryption scheme called AES-XTS. The WireTap setup allows attackers to observe these encrypted memory transactions in real-time. By carefully controlling an SGX enclave and forcing it to perform cryptographic operations, the researchers were able to mount a ciphertext side-channel attack. They observed the encrypted memory traffic during the generation of an ECDSA signature, a process used for SGX attestation. This allowed them to build a dictionary of ciphertexts and recover the secret nonce used in the signing operation. With the nonce and the public signature, they successfully extracted the machine’s private DCAP attestation key from a fully trusted server in under 45 minutes.

The consequences of extracting an SGX attestation key are severe, particularly for the blockchain and Web3 ecosystems that rely on SGX for security. The researchers demonstrated end-to-end attacks on several real-world SGX deployments. For privacy-preserving smart contract networks like Phala and Secret, a compromised key would allow an attacker to forge quotes, run malicious enclaves, and extract master keys, enabling network-wide decryption of confidential transactions. On decentralized storage networks like Crust, an attacker could fake proofs of storage, allowing them to claim financial rewards without actually storing any data, thereby breaking the system’s integrity guarantees.

To read the complete article see: [Cyber Security News](https://cybersecuritynews.com/new-wiretap-attack/)