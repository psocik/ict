---
title: First Public Kernel Memory Corruption
date: 2026-05-16
categories: [SECURITY]
tags: [KERNEL,MEMORY,EXPLOIT,MACOS,SECURITY]
---

## First Public Kernel Memory Corruption 🚀

Apple has spent five years developing hardware and software to make memory corruption exploits significantly harder. However, our engineers, in collaboration with Mythos Preview, managed to create a working exploit in just five days!

Memory corruption remains the most common vulnerability class across all platforms, including iOS and macOS. The latest flagship example is **MIE (Memory Integrity Enforcement)**, Apple's hardware-assisted memory safety system built around ARM's **MTE (Memory Tagging Extension)**. This system was introduced as a key security feature for the Apple M5 and A19 chips, specifically designed to thwart memory corruption exploits, which are behind many sophisticated compromises on iOS and macOS.

Our macOS attack path was an accidental discovery. Bruce Dang found the bugs on April 25th, and with the help of Dion Blazakis and Josh Maine, we had a working exploit by May 1st. This exploit is a data-only kernel local privilege escalation chain targeting macOS 26.4.1 (25E253). It starts from an unprivileged local user, utilizes only normal system calls, and culminates in a root shell.

Mythos Preview played a crucial role in identifying the bugs and assisting throughout the exploit development. They quickly discovered the vulnerabilities because they belong to known bug classes. However, bypassing MIE, a new best-in-class mitigation, proved to be challenging. Our motivation was to explore the possibilities when top models are paired with expert knowledge. Achieving a kernel memory corruption exploit against the best protections in just a week is a significant accomplishment!

To the best of our knowledge, this is the first public macOS kernel exploit on MIE hardware. MIE was never intended to be hacker-proof; with the right vulnerabilities, it can be bypassed. AI systems are continuously discovering more vulnerabilities, and it's only a matter of time before some of these bugs are powerful enough to overcome advanced mitigations like MIE. This is precisely what we have just uncovered.

[Read full article](https://blog.calif.io/p/first-public-kernel-memory-corruption)