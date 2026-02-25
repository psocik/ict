---
title: 341 Malicious ClawHub Skills Discovered Stealing User Data
date: 2026-02-02
categories: [CYBERSECURITY]
tags: [MALWARE,CLAWHUB,SECURITY,DATA THEFT]
---

## Researchers Uncover Malicious Skills on ClawHub 🚨

A recent security audit of **2,857 skills** on ClawHub has revealed **341 malicious skills** across various campaigns, according to findings from Koi Security. This alarming discovery exposes users to significant supply chain risks. ClawHub serves as a marketplace for **OpenClaw** users, a self-hosted AI assistant, to find and install third-party skills.

The analysis indicates that **335 skills** utilize fake prerequisites to install a macOS stealer known as **Atomic Stealer (AMOS)**, part of a campaign dubbed **ClawHavoc**.

> "You install what looks like a legitimate skill – maybe solana-wallet-tracker or youtube-summarize-pro," said Koi researcher **Oren Yomtov**. "The skill's documentation appears professional. However, there's a 'Prerequisites' section that instructs users to install something first."

### Installation Instructions 📥

For Windows users, the instructions direct them to download a file named **openclaw-agent.zip** from a GitHub repository. Meanwhile, macOS users are instructed to copy an installation script hosted at **glot[.]io** and paste it into the Terminal app.

This script fetches next-stage payloads from an attacker-controlled infrastructure, reaching out to the IP address **91.92.242[.]30** to obtain a universal Mach-O binary consistent with **Atomic Stealer**. This commodity stealer can harvest data from macOS hosts. 

These malicious skills often disguise themselves as ClawHub typosquats or cryptocurrency and trading tools. A security researcher summarized the threat, stating, "All these skills share the same command-and-control infrastructure (91.92.242[.]30) and employ sophisticated social engineering tactics to convince users to execute malicious commands, leading to the theft of crypto assets such as exchange API keys, wallet private keys, SSH credentials, and browser passwords."

### Reporting Feature Introduced 🛡️

Due to ClawHub's open nature, allowing anyone to upload skills, OpenClaw's creator **Peter Steinberger** has implemented a reporting feature. "Each user can have up to **20 active reports** at a time," the documentation states. "Skills with more than **3 unique reports** are auto-hidden by default."

Open-source ecosystems continue to be exploited by threat actors, who are now leveraging OpenClaw's rising popularity to orchestrate malicious campaigns. **Palo Alto Networks** has warned that OpenClaw represents a **'lethal trifecta'** that makes AI agents inherently vulnerable due to their access to private data, exposure to untrusted content, and the ability to communicate externally. This situation enables time-shifted prompt injection, memory poisoning, and logic bomb-style activation, where the exploit is created at ingestion but detonates only when the agent's internal state, goals, or tool availability align.

For more details, check out the complete article here: [Read full article](https://thehackernews.com/2026/02/researchers-find-341-malicious-clawhub.html)