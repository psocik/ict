---
title: Cloudflare-Themed ClickFix Attack Drops Infiniti Stealer on Macs
date: 2026-03-28
categories: [CYBERSECURITY]
tags: [CLOUDFLARE,MALWARE,MACOS,INFINITI STEALER,CYBERSECURITY]
---

## Cloudflare-Themed ClickFix Attack Drops Infiniti Stealer on Macs 🚨

macOS users are targeted in a fresh ClickFix campaign that uses a Cloudflare-themed verification page to deliver a Python-based information stealer, Malwarebytes reports.

The attack starts with a fake CAPTCHA page that serves a legitimate-looking Cloudflare human verification page asking visitors to paste and execute a command in Terminal. 

Referred to as ClickFix, the technique relies on social engineering to trick users into executing malicious commands on their devices and has been widely used in attacks since August 2024, mainly against Windows users.

For more than half a year, however, attacks tailored for macOS have become increasingly convincing, and the variant observed by Malwarebytes is no different.

The Python-based information stealer targets:
- Browser credentials
- Keychain information
- Cryptocurrency wallets
- Secrets stored in developer files
- Screenshots captured during execution

“Infiniti Stealer shows how techniques that worked on Windows—like ClickFix—are now being adapted to target Mac users. It also uses newer techniques, like compiling Python into native apps, which makes the malware harder to detect and analyze. If this approach proves effective, we may see more attacks like this,” Malwarebytes notes. 

[Read full article](https://www.securityweek.com/cloudflare-themed-clickfix-attack-drops-infiniti-stealer-on-macs/)