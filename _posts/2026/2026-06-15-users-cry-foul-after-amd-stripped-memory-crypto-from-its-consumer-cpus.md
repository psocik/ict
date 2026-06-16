---
title: Users Cry Foul After AMD Stripped Memory Crypto from Its Consumer CPUs
date: 2026-06-15
categories: [TECHNOLOGY]
tags: [AMD,MEMORY,CRYPTO,CPUS,SECURITY]
---

## Users Cry Foul After AMD Stripped Memory Crypto from Its Consumer CPUs

A decade ago, AMD introduced a protection mechanism to its high-end CPUs to safeguard against cold boot attacks and other physical exploits that could extract sensitive data from connected memory chips. This feature, known as **Transparent Secure Memory Encryption (TSME)**, encrypts the entire contents stored in memory, rendering the data useless to physical attackers. Over time, AMD extended TSME to lower-end processors, including the consumer version of its Ryzen chips, which are more affordable than the Pro versions. Users of these lower-end chips have come to rely on this added security.

However, recently and without any prior notice, AMD has removed this protection from its lower-end line of CPUs. This change was implemented in a manner that was difficult to detect on Windows machines and required significant technical effort to identify on Linux systems.

AMD has not provided an explanation for why TSME was previously available on these CPUs, nor has it confirmed the change. In a brief response to inquiries, AMD stated that TSME "is a security feature only applied to PRO CPUs as part of AMD PRO Technologies." This marks the first time the company has publicly acknowledged this restriction.

The removal of TSME was first discovered in April by Ben Kilpatrick, a self-described "privacy-conscious Linux hobbyist." While installing a new operating system on his Ryzen 7 9700X, Kilpatrick ran the Host Security ID (HSI) audit feature to verify that all security protections were enabled. To his surprise, HSI indicated that TSME was no longer supported, displaying the message "encrypted RAM: not supported." Previously, TSME had been shown as "encrypted," which left Kilpatrick puzzled since he had enabled TSME in his BIOS settings all along.

🚀 This situation has sparked significant concern among users who rely on AMD's CPUs for their security needs. 

[Read full article](https://arstechnica.com/security/2026/06/users-cry-foul-after-amd-stripped-memory-crypto-from-its-consumer-cpus/)