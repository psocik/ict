---
title: New DDRop Attack Breaks Intel TDX and AMD SEV-SNP
date: 2026-09-14
categories: [CONFIDENTIAL COMPUTING]
tags: [DDROP,INTEL,AMD,ATTACK,CLOUD,SECURITY]
---

## New DDRop Attack Breaks Intel TDX and AMD SEV-SNP

Researchers have disclosed a new hardware attack, called **DDrop**, that breaks the memory protection in Intel and AMD confidential computing by silently dropping writes to a server's memory. This allows the processor to keep reading old encrypted data as if it were current. The attack requires an attacker who already controls the server's software and can briefly access the machine to insert a small circuit board, called an interposer, between the processor and a memory module. The interposer costs under $200 to build. 

### How DDRop Works
DDrop works against Intel TDX, Intel Scalable SGX, and AMD SEV-SNP, which are widely used by cloud services. Confidential computing designs omit a guarantee called **freshness**, which DDRop exploits. When the interposer drops a write, the earlier value stays in memory, and the processor reads it back as though the update had happened.

### Significance of DDRop
DDrop is the first active interposer attack to work on the DDR5 memory in today's cloud servers. It breaks the integrity of an up-to-date Intel TDX system rather than only reading data from it. Earlier DDR5 interposer attacks, such as TEE.fail, were passive. Active attacks like Battering RAM worked only on older DDR4. DDRop circumvents DDR5's redesigned command format by dropping writes instead. 

### Attack Mechanism
The interposer is a small board of switches that sits on the memory bus and runs at full DDR5 speed. To drop a write, it forces an error on the command bus and then cuts the wire the memory module uses to report that error, causing the module to quietly discard the command without notifying the processor.

### Implications for Virtual Machines
On Intel TDX, the researchers turned write-dropping into full control of a protected virtual machine. With that access, they read a victim virtual machine's private memory and switched it into debug mode, allowing them to copy its memory in plaintext and restore the original data so the victim showed no sign of tampering. On AMD SEV-SNP, dropping writes during AMD's page-relocation feature enabled the researchers to copy the contents of one victim page into another. However, debug-mode and attestation-forgery attacks are specific to Intel TDX. All three technologies encrypt memory without the freshness check that DDRop exploits, making them vulnerable.

### Mitigation Challenges
There is no simple patch for this vulnerability. The weakness lies in the hardware design, and closing the gap for good would require new memory-encryption hardware that adds both integrity and freshness. Software changes can raise the bar without removing the root cause, including restricting the memory-management features DDRop abuses, checking that important writes actually landed, and looking for an interposer during boot.

Intel and AMD were informed about DDRop in advance through coordinated disclosure, and both acknowledged the findings. They state that because the attack requires physical access to the system, it falls outside the scope of their published threat models for SEV/SNP and server memory. The access required could come from a rogue data-center employee, tampering in the supply chain, or hardware seized under legal compulsion.

For more details, you can read the complete article here: [Read full article](https://thehackernews.com/2026/09/new-ddrop-attack-breaks-intel-tdx-and.html) 
