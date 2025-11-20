---
title: Researchers Detail Tuoni C2's Role in an Attempted 2025 Real-Estate Cyber Intrusion
date: 2025-11-18
categories: [CYBERSECURITY]
tags: [TUONI C2,CYBERSECURITY,REAL ESTATE,CYBER ATTACK]
---

A U.S. real-estate company was targeted in a cyberattack in mid-October 2025, with the attackers employing the emerging Tuoni command-and-control (C2) framework. Cybersecurity researchers at Morphisec disclosed details of the attempted intrusion, highlighting the use of this relatively new red teaming tool in a real-world malicious campaign. Tuoni, which has a free "Community Edition" available on GitHub, is designed for penetration testing, red team engagements, and security assessments, but is increasingly being abused for nefarious purposes.

The attack sequence likely began with social engineering via Microsoft Teams impersonation. The threat actors likely impersonated trusted vendors or colleagues, tricking an employee into running a malicious PowerShell command. This command downloaded a second PowerShell script from an external server, kupaoquan[.]com. This script then used steganography to conceal the next-stage payload within a bitmap image (BMP). The goal was to extract shellcode and execute it directly in memory, leading to the execution of TuoniAgent.dll.

TuoniAgent.dll is an agent that operates within the targeted machine, connecting to the C2 server, kupaoquan[.]com, to enable remote control. While the attack was ultimately unsuccessful, it illustrates the risks associated with the misuse of red teaming tools. Researchers observed that the delivery mechanism showed signs of AI assistance in code generation, based on the scripted comments and modular structure of the initial loader, raising concerns about the increasing sophistication and accessibility of offensive cyber capabilities.

This incident is not isolated. In September 2025, Check Point researchers reported the use of HexStrike AI, an artificial intelligence (AI)-powered tool, to streamline and accelerate vulnerability exploitation. Security professionals should be aware of the potential for red teaming tools like Tuoni to be weaponized and used in real-world attacks. Monitoring network traffic for connections to known Tuoni C2 servers and examining PowerShell scripts for steganographic techniques can aid in detection. Organizations should also reinforce social engineering awareness training to prevent initial access.

To read the complete article see: [The Hacker News](https://thehackernews.com/2025/11/researchers-detail-tuoni-c2s-role-in.html) 

---