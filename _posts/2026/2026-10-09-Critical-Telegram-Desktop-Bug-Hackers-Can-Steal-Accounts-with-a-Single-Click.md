---
title: Critical Telegram Desktop Bug Hackers Can Steal Accounts with a Single Click
date: 2026-10-09
categories: [SECURITY]
tags: [TELEGRAM,HACKERS,VULNERABILITY,CYBERSECURITY]
---

## Critical Telegram Desktop Bug: Hackers Can Steal Accounts with a Single Click 🚨

A severe vulnerability has been discovered in Telegram Desktop versions prior to 7.2.9, released on September 17, 2026. Hackers can exploit this critical bug to hijack accounts and exfiltrate user files with just a single click! 

### What Happens?

When someone adds you to a Telegram group, a link appears in the chat. If you click it, your Telegram account could be compromised. A security researcher, known as BeakSEK, explains, **"Your Telegram account is no longer only yours."** This vulnerability has been rated 8.6 out of 10 on the CVSS severity scale and is identified as CVE-2026-10718.

### How Does It Work?

The vulnerability arises because vulnerable versions of Telegram Desktop do not properly handle certain characters in links, specifically failing to escape semicolons. This allows hackers to craft malicious `tg://` links that can execute harmful commands. For instance, an attacker can send a link with malicious commands separated by semicolons, tricking the application into treating them as legitimate commands.

### The Attack Process

1. An attacker creates a supergroup on Telegram and adds victims.
2. The attacker posts crafted instruction `.txt` files, which Telegram automatically downloads to the victim's machines.
3. The attacker then shares a seemingly harmless link that redirects to a malicious `tg:` link containing injected commands.
4. If a victim clicks it, their system launches a second Telegram process, executing the commands and leaking files that allow the hacker to recover the session and the victim's account.

### What Can You Do?

To mitigate this risk, BeakSEK urges users to:
- Update Telegram Desktop apps to the latest version.
- Limit who can add you to groups.
- Set a local passcode.
- Enable the option to **"ask where to save each file"** to prevent automatic downloads.

Stay safe and protect your accounts! 🔒

[Read full article](https://cybernews.com/security/one-click-telegram-desktop-exploit-hijacks-accounts/) 
