---
title: New Yurei Ransomware With PowerShell Commands Encrypts Files With ChaCha20 Algorithm
date: 2025-09-15
categories: [CYBERSECURITY]
tags: [RANSOMWARE,YUREI,CYBERSECURITY NEWS]
---

Emerging in early September 2025, the Yurei ransomware has swiftly drawn attention for its novel combination of Go-based execution and ChaCha20 encryption.

At its core, Yurei leverages Go’s concurrency features to enumerate all drives in parallel and encrypt files with the ChaCha20 algorithm. For each file, a new random ChaCha20 key and nonce are generated, then encrypted using ECIES with the attacker’s public key.

Check Point researchers noted that Yurei retains symbols in the binary, a mistake inherited from the Prince-Ransomware builder, which did not strip debugging information.

In the context of defensive strategies, Yurei’s failure to remove Volume Shadow Copies reveals a critical weakness.

[Read the full article here](https://cybersecuritynews.com/new-yurei-ransomware-with-powershell-commands/) 😊