---
title: RMPocalypse Single 8-Byte Write Shatters AMD's SEV-SNP Confidential Computing
date: 2025-10-14
categories: [SECURITY]
tags: [VULNS,CONFIDENTIAL COMPUTING,AMD]
---

The attack, per ETH Zürich researchers Benedict Schlüter and Shweta Shinde, exploits AMD's incomplete protections that make it possible to perform a single memory write to the Reverse Map Paging (RMP) table, a data structure that's used to store security metadata for all DRAM pages in the system.

At the heart of the problem is a lack of adequate safeguards for the security mechanism itself -- something of a catch-22 situation that arises as a result of RMP not being fully protected when a virtual machine is started, effectively opening the door to RMP corruption.

"This gap could allow attackers with remote access to bypass certain protective functions and manipulate the virtual machine environment, which is intended to be securely isolated," Zürich said. "This vulnerability can be exploited to activate hidden functions (such as a debug mode), simulate security checks (so-called attestation forgeries) and restore previous states (replay attacks) – and even to inject foreign code."

"RMPocalypse shows that AMD's platform protection mechanisms are not complete, thus leaving a small window of opportunity for the attacker to maliciously overwrite the RMP on initialization," the researchers said. "Due to the design of the RMP, a single overwrite of 8 bytes within the RMP causes the entire RMP to become subsequently compromised."  "With a compromised RMP, all integrity guarantees of SEV-SNP become void. RMPocalypse case studies show that an attacker-controlled RMP not only voids the integrity but also results in a full breach of confidentiality."

To read the complete article see: [The Hacker News](https://thehackernews.com/2025/10/rmpocalypse-single-8-byte-write.html)