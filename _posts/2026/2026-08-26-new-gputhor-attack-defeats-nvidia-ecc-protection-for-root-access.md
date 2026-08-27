---
title: New GPUThor Attack Defeats NVIDIA ECC Protection for Root Access
date: 2026-08-26
categories: [SECURITY]
tags: [GPU,NVIDIA,SECURITY,ATTACK,RESEARCH]
---

## New GPUThor Attack Defeats NVIDIA ECC Protection for Root Access

A newly disclosed Rowhammer attack called **GPUThor** can bypass error-correcting code (ECC) protections on NVIDIA GPUs, enabling denial-of-service (DoS) and root-level privilege escalation. In a paper published by the University of Toronto, researchers say that GPUThor achieves far more practical bit-flip rates than past concepts. 

The attack was demonstrated against Ampere-class NVIDIA workstation GPUs with GDDR6 memory, including the RTX A4000, RTX A4500, RTX A5000, and RTX A6000, all widely used in AI and cloud infrastructure. Rowhammer is the name for a class of attacks where memory rows are repeatedly accessed ("hammered") in a way that increases the likelihood of bits in neighboring memory regions to flip, changing their state from one to zero or vice versa. This can lead to data corruption and security risks. Since AI model training relies heavily on GPU power, a successful Rowhammer attack could have a devastating impact on the model's accuracy. 🚀

To mitigate risks from this type of attack, NVIDIA uses mitigations such as SECDED ECC to correct single-bit errors and detect double-bit errors within monitored memory blocks. However, University of Toronto researchers adjusted GPUThor so its hammering follows a non-uniform pattern at a rate that avoids activating GDDR6's Target Row Refresh (TRR) mitigations. The researchers say that compared to previous attack concepts, the adjustment leads to generating 6.6 times more aggressor-row activations and achieves between 72,000 and 377,000 flips per GB on the tested GPUs with no ECC protections. At GPUThor bit-flip rates, finding an exploitable bit flip is possible within roughly 1.1 minutes, down from 21.9 hours with GPUHammer. 

The researchers explain that with ECC enabled, GPUThor generated 387 double-bit errors that ECC detects but cannot correct, and two triple-bit errors, which ECC repaired incorrectly, resulting in data corruption. 

University of Toronto researchers showed that GPUThor can induce a DoS state on an ECC-enabled RTX A6000, causing the GPU to reset every two hours and terminating all workloads. The more interesting attack is escalating privileges to root level, which the researchers claim is possible by corrupting GPU page tables, giving an unprivileged CUDA program arbitrary memory access and opening a root shell on the host system. 

Beyond the four models confirmed to be vulnerable to GPUThor, the researchers say that despite limitations that improve resilience to denial-of-service (DoS) conditions, privilege escalation can still work on server-class Ampere GPUs (A100) because they still rely on SECDED-level ECC. In the case of some Blackwell GPUs, the RAS Repair resilience feature makes a GPUThor attack more time-consuming but does not prevent it. 

According to the researchers' GPUThor paper published yesterday, even HBM3/e and GDDR7 GPUs with on-die ECC might be vulnerable if multi-bit flips are triggered. 

The researchers reported their findings to NVIDIA on April 29, and on August 21, the company published an advisory providing guidance. NVIDIA recommends enabling both SYS-ECC and IOMMU/DMA isolation, monitoring GPU error telemetry, and restricting the sharing or execution of untrusted workloads. The researchers recommend avoiding cross-tenant GPU sharing where possible, monitoring ECC error counters, and restricting untrusted CUDA workloads. They added that complete protection will likely require stronger multi-bit ECC and hardware-level defenses in future GPUs. 

[Read full article](https://www.bleepingcomputer.com/news/security/new-gputhor-attack-defeats-nvidia-ecc-protection-for-root-access/)