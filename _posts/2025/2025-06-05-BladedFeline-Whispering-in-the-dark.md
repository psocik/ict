---
title: BladedFeline Whispering in the dark
date: 2025-06-05
categories: [APT]
tags: [ESET,BLADEDFELINE,MALWARE,APT GROUP]
---

In 2024, ESET researchers discovered several malicious tools in the systems used by Kurdish and Iraqi government officials. The APT group behind the attacks is BladedFeline, an Iranian threat actor that has been active since at least 2017, when it compromised officials within the Kurdistan Regional Government (KRG). This group develops malware for maintaining and expanding access within organizations in Iraq and the KRG. While this is our first blog post covering BladedFeline, we discovered the group in 2023, after it targeted Kurdish diplomatic officials with the Shahmaran backdoor, and previously reported on its activities in ESET APT Activity Reports Q4 2023-Q1 2024 and Q2 2024-Q3 2024.

The array of tools utilized in the recent campaign shows that since deploying Shahmaran, BladedFeline has continued to develop its arsenal. We found two reverse tunnels, a variety of supplementary tools, and most notably, a backdoor that we named Whisper and a malicious IIS module we dubbed PrimeCache. Whisper is a backdoor that logs into a compromised webmail account on a Microsoft Exchange server and uses it to communicate with the attackers via email attachments. PrimeCache also serves as a backdoor: it is a malicious IIS module related to what we referred to as Group 2 in our 2021 paper "Anatomy of native IIS malware." Significantly, PrimeCache also bears similarities to the RDAT backdoor used by the Iran-aligned OilRig APT group.

To read the complete article see: [BladedFeline: Whispering in the dark](https://www.welivesecurity.com/en/eset-research/bladedfeline-whispering-dark/) 