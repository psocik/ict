---
title: Turla Cereal Tricks
date: 2026-11-10
categories: [CYBERSECURITY]
tags: [MALWARE,TURLA,CYBERESPIONAGE,APT]
---

## Turla Cereal Tricks

On **November 28th, 2025**, we detected a previously undocumented set of malicious tools being actively used against a governmental organization in Kazakhstan. None of the initially visible components looked like a standalone backdoor, but instead appeared to be pieces of a larger chain: encrypted payloads, in-memory .NET assemblies, and legitimate Windows and Exchange processes being used to execute malicious code. After fine-tuning our detections, we found the same toolset at a governmental organization in Romania, compromised from **December 23rd, 2025** onwards. In both cases, the attackers focused on Exchange servers. We attribute this toolset to the Russia-aligned advanced persistent threat (APT) group **Turla** with high confidence, based on its co-occurrence with known Turla malware and similarities to a Turla malware family documented in 2017.

As we reconstructed the activity, the toolset revealed itself as modular and tightly interconnected. Most components are .NET assemblies that are never written to disk; instead, they are decrypted, deserialized, loaded into memory, and executed by other components. Because of this heavy reliance on serialization, we have given these tools names that start with the prefix **"Cereal"**. The tools are tightly interconnected and sometimes delivered in an intricate chain of components. They were designed to be stealthy, with long-term cyberespionage in mind. No external network infrastructure was observed.

Some aspects make this toolset particularly noteworthy. One component, **CerealNeuron**, is a passive backdoor running on Exchange servers and waiting for incoming requests, without relying on external command and control (C&C) infrastructure. In practice, this means that the victim's own Exchange server is abused as an operator-accessible control point, blending malicious traffic with legitimate Exchange web services and reducing the attacker's dependence on infrastructure that could be discovered, blocked, or taken down. Another component, **CerealBox**, is injected into Microsoft Exchange's transport service to filter and collect email messages directly from the email flow - a novel technique that requires deep knowledge of Exchange internals.

An automated email collection module, injected into legitimate Microsoft Exchange processes, accesses and manipulates the email transport pipeline: this requires deep understanding of the inner workings of Microsoft Exchange and is a novel technique. Developed for extensibility, the toolset makes heavy use of abstraction and decoupling mechanisms to separate core functionality from specific implementations, so features can be swapped out without modifying the main execution logic. The use of various .NET tricks, such as unmanaged entry points, and abuse of the .NET native image cache, makes this toolset quite sophisticated in comparison to most recent APT cases that we have researched. Abuse of victim-controlled Exchange infrastructure to distribute commands in the local network is a rare technique employed by only a small number of APT groups.

[Read full article](https://web-assets.esetstatic.com/wls/en/papers/white-papers/turla-cereal-tricks.pdf)\n