---
title: $50 Battering RAM Attack Breaks Intel and AMD Cloud Security Protections
date: 2025-09-30
categories: [SECURITY]
tags: [MALWARE,INTEL,AMD,CLOUD SECURITY]
---

The attack, in a nutshell, involves leveraging a custom-built, low-cost DDR4 interposer hardware hack to stealthily redirect physical addresses and gain unauthorized access to protected memory regions. The interposer makes use of simple analog switches to actively manipulate signals between the processor and memory, and can be built for less than $50.

Researchers Jesse De Meulemeester, David Oswald, Ingrid Verbauwhede, and Jo Van Bulck stated, "We built a simple, $50 interposer that sits quietly in the memory path, behaving transparently during startup and passing all trust checks. Later, with just a flip of a switch, our interposer turns malicious and silently redirects protected addresses to attacker-controlled locations, allowing corruption or replay of encrypted memory."

On Intel platforms, Battering RAM achieves arbitrary read access to victim plaintext or write plaintext into victim enclaves, whereas on AMD systems, the attack can sidestep recent firmware mitigations against BadRAM and introduce arbitrary backdoors into the virtual machine without raising any suspicion.

"Battering RAM exposes the fundamental limits of the scalable memory encryption designs currently used by Intel and AMD, which omit cryptographic freshness checks in favor of larger protected memory sizes," the researchers added. "Battering RAM is capable of introducing memory aliases dynamically at runtime. As a result, Battering RAM can circumvent Intel's and AMD's boot-time alias checks."

To read the complete article, see: [The Hacker News](https://thehackernews.com/2025/10/50-battering-ram-attack-breaks-intel.html) 😊