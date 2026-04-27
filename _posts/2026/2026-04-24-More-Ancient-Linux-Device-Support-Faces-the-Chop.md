---
title: More Ancient Linux Device Support Faces the Chop
date: 2026-04-24
categories: [TECHNOLOGY]
tags: [LINUX,VULNERABILITY,DRIVERS,TECHNOLOGY]
---

## More Ancient Linux Device Support Faces the Chop 🚀

One tactic to deal with LLM-powered vulnerability detection is simple - just speed up the removal of old code. If it's gone, it no longer matters if it's buggy. Bot-powered bug-busting is in the news of late, with scary-sounding reports of automated tools detecting flaws and vulnerabilities far faster than any unaided humans. Some of these are long-standing howlers, such as a 27-year-old bug in OpenBSD and a 23-year-old flaw in the Linux in-kernel NFS code.

The good news is that there's one fairly dramatic but simple approach to handling this: if the bugs are in very old drivers for very old hardware, then don't even try to fix them - just remove them. This is a theme behind multiple recent changes in the kernel.

Andrew Lunn's 18-patch series removes the drivers for 3Com's 3C509, 3C515, 3C574, 3C589, and 3C59x hardware. It also removes 13 other devices, including some old Xircom parallel-port and PCMCIA slot cards. Also up for the chop are some newer - but still over two decades old - cards: the Hamachi and Yellowfin PCI gigabit adaptors. The AX.25 and HAM Radio drivers are also slated to go, as is Asynchronous Transfer Mode networking. ISDN CAPI support looks set to go, as well, including over Bluetooth. Linux benchmarking and news site Phoronix reckons just the Ethernet devices will remove nearly 30,000 lines of code.

Another device-support removal that may happen in kernel 7.1 is one that was last proposed almost a year ago for kernel 6.15: removal of 80486 support. It wasn't new last year, either - the change was already being discussed in 2022. Even if all these changes are approved, it doesn't spell instant doom: old kernels with the support present will still be maintained for years to come.

The Register also heard from René Rebe, lead maintainer of the T2 distribution, who told us: "Just wanted to let you know that T2/Linux will of course continue to support this. It's trivial to support early and simple 32-bit CPUs. We provided i486 releases all the last years, recently fixed some bugs, and still run it on the fastest i486 class CPUs (AMD 5x86) overclocked at 160 MHz, or Vortex86 Embedded and Industrial boards."  

[Read full article](https://www.theregister.com/2026/04/24/ancient_linux_drivers_going/)