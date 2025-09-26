---
title: Critical CVSS 10 Flaw in GoAnywhere File Transfer Threatens 20,000 Systems
date: 2025-09-25
categories: [VULNS]
tags: [CVSS,GOANYWHERE,FORTRA,VULNERABILITY]
---

Urgent warning for Fortra GoAnywhere MFT users. A CVSS 10.0 deserialization vulnerability (CVE-2025-10035) in the License Servlet allows command injection. Patch to v7.8.4 immediately to prevent system takeover.

The flaw allows a malicious individual to trick the software during the deserialization process by using a "validly forged license response signature" to load a harmful object. This can lead to command injection, allowing an attacker to run their own code on the system.

According to a long technical analysis from watchTowr Labs, shared with Hackread.com, the gravity of the situation is highlighted, noting that there are "over 20,000 instances exposed to the Internet, a playground APT groups dream about."

This isn’t the first time we’ve seen this; back in 2023, a similar pre-authentication command injection flaw (CVE-2023-0669) in the same product was widely exploited by the cl0p ransomware gang.

[Read the complete article here](https://hackread.com/critical-cvss-10-flaw-goanywhere-file-transfer/).