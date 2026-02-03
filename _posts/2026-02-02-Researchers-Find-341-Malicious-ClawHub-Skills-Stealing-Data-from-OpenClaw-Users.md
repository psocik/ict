---
title: Researchers Find 341 Malicious ClawHub Skills Stealing Data from OpenClaw Users
date: 2026-02-02
categories: [SECURITY]
tags: [MALWARE,CLAWHUB,DATA THEFT,OPENCLAW]
---

A security audit of 2,857 skills on ClawHub has found 341 malicious skills across multiple campaigns, according to new findings from Koi Security, exposing users to new supply chain risks. ClawHub is a marketplace designed for OpenClaw users, a self-hosted artificial intelligence (AI) assistant, to find and install third-party skills. The analysis found that 335 skills use fake prerequisites to install an Apple macOS stealer named Atomic Stealer (AMOS), a campaign codenamed ClawHavoc.

Koi researcher Oren Yomtov explained, "You install what looks like a legitimate skill – maybe solana-wallet-tracker or youtube-summarize-pro. The skill's documentation looks professional. But there's a 'Prerequisites' section that says you need to install something first." This step involves instructions for both Windows and macOS systems: On Windows, users are asked to download a file called "openclaw-agent.zip" from a GitHub repository. On macOS, the documentation tells them to copy an installation script hosted at glot[.]io and paste it into the Terminal app.

For macOS, the glot[.]io script fetches next-stage payloads from an attacker-controlled infrastructure, reaching out to IP address "91.92.242[.]30" to obtain a universal Mach-O binary consistent with Atomic Stealer, a commodity stealer that can harvest data from macOS hosts. These malicious skills often masquerade as ClawHub typosquats or cryptocurrency and trading tools. A security researcher summarized the threat by stating, "All these skills share the same command-and-control infrastructure (91.92.242[.]30) and use sophisticated social engineering to convince users to execute malicious commands, which then steal crypto assets like exchange API keys, wallet private keys, SSH credentials, and browser passwords."

Due to ClawHub being open by default, allowing anyone to upload skills, OpenClaw's creator Peter Steinberger rolled out a reporting feature. "Each user can have up to 20 active reports at a time," the documentation states. "Skills with more than 3 unique reports are auto-hidden by default." Open-source ecosystems continue to be abused by threat actors, who are now piggybacking on OpenClaw's sudden popularity to orchestrate malicious campaigns. Palo Alto Networks warned that OpenClaw represents a "lethal trifecta" that renders AI agents vulnerable by design due to their access to private data, exposure to untrusted content, and the ability to communicate externally. This facilitates time-shifted prompt injection, memory poisoning, and logic bomb–style activation, where the exploit is created at ingestion but detonates only when the agent's internal state, goals, or tool availability align.

To read the complete article see: [The Hacker News](https://thehackernews.com/2026/02/researchers-find-341-malicious-clawhub.html)