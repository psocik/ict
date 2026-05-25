---
title: An Example of Stack String in High Level Language
date: 2026-05-23
categories: [CYBERSECURITY]
tags: [MALWARE,STACK-STRINGS,HIGH-LEVEL-LANGUAGE,REVERSE-ENGINEERING]
---

## An Example of Stack String in High Level Language

This week, I'm attending the SEC670 training (**Red Teaming Tools - Developing Windows Implants, Shellcode, Command and Control**). From my perspective, this training aligns perfectly with FOR610 or FOR710 (malware analysis) because it addresses malware from the opposite angle: instead of performing reverse engineering, you write malicious code! It's always fascinating to gain another perspective. 🚀  

Many techniques used by threat actors are often discovered while reversing malware code and are read in assembly. A perfect example is stack strings. This is a malware obfuscation technique where strings are constructed dynamically at runtime by assigning individual characters or bytes directly onto the stack, rather than storing them as contiguous string literals in the binary's static data sections. In simpler terms, they won't be detected by basic tools like 'strings' or 'pestr'. For instance, the string "sans isc" will be printed on the console.  

But how do you implement this in a high-level language like C? Once compiled, let's disassemble it with Ghidra. As expected, the first string is directly discovered. Now, let's try to find the second string. It's not directly available. The stack string is generated with the code below. Characters are moved one by one (0x68, 0x74, 0x74, ...). Because characters are hex-encoded, it makes them even more difficult to spot by the reverse engineer's eyes.  

Of course, we are lazy people and we need tools and processes to spot such types of strings. We have tools to do this, like floss. But to better understand how we can spot them, let's take a look at a "manual" technique. Because bytes are moved one by one on the stack, the ASM instruction used is "movb" or "mov BYTE PTR" (depending on the syntax convention, AT&T or Intel). Magic! So /bin/bash can be considered a reverse-engineering tool :-).

[Read full article](https://isc.sans.edu/forums/diary/An%20Example%20of%20Stack%20String%20in%20High%20Level%20Language/33008/)