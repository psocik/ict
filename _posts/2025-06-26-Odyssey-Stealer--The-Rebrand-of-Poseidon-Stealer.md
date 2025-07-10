---
title: Odyssey Stealer  The Rebrand of Poseidon Stealer
date: 2025-06-26
categories: [CYBERSECURITY]
tags: [MALWARE,ODYSSEY STEALER,POSEIDON STEALER,CYFIRMA,CYBERSECURITY]
---

**EXECUTIVE SUMMARY**  
The CYFIRMA research team has uncovered multiple websites employing Clickfix tactics to deliver malicious AppleScripts (osascripts). These scripts contain commands designed to steal browser cookies, passwords, cryptocurrency wallet data, and browser plugins. We’ve identified a command-and-control panel linked to this activity, which is attributed to Odyssey Stealer. The malicious websites we’ve observed are primarily typosquatting finance domains, Apple App Store domains, or cryptocurrency news-related domains. This suggests that the malware operators are likely targeting individuals interested in finance and cryptocurrency.  

**INTRODUCTION**  
The Odyssey Stealer is distributed using the Clickfix technique. The Clickfix technique begins with the creation of a typosquatted or visually similar domain, designed to exploit user errors when typing. When a user inadvertently visits this malicious domain, they are presented with a fake Cloudflare-style CAPTCHA prompt.  

Below the prompt, instructions are displayed for macOS users to copy a command and paste it into the terminal. If accessed from a Windows device, the site provides Windows-specific instructions instead. However, during our analysis, clicking the “Copy” button did not copy any commands. Since the Odyssey Stealer currently targets macOS, it’s possible that future updates may expand its capabilities to target Windows systems.  

To read the complete article see: [Odyssey Stealer : The Rebrand of Poseidon Stealer](https://www.cyfirma.com/research/odyssey-stealer-the-rebrand-of-poseidon-stealer/)  

***Working at Team Cymru is more than a job — it’s a chance to be part of something meaningful. Enjoy outstanding benefits, work with incredible people, and contribute to a mission that truly matters. Explore open roles and join us: [Team Cymru Careers](https://www.team-cymru.com/careers)***