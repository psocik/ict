---
title: RansomHouse upgrades encryption with multi-layered data processing
date: 2025-12-20
categories: [SECURITY]
tags: [RANSOMWARE,ENCRYPTION,CYBERSECURITY]
---

The RansomHouse ransomware-as-a-service (RaaS) has recently upgraded its encryptor, switching from a relatively simple single-phase linear technique to a more complex, multi-layered method. RansomHouse’s latest encryptor variant switches from a single-pass file data transformation to a two-stage transformation that leverages two keys, a 32-byte primary and an 8-byte secondary key. The second major upgrade is the introduction of a new file processing strategy that uses dynamic chunk sizing at a threshold of 8GB, with intermittent encryption. Unit 42 says this makes static analysis more difficult due to its non-linearity, use of complex math to determine the processing order, and the use of distinct approaches for each file based on its size. 

To read the complete article see: [Bleeping Computer](https://www.bleepingcomputer.com/news/security/ransomhouse-upgrades-encryption-with-multi-layered-data-processing/) 