---
title: Mac users warned about new DigitStealer information stealer
date: 2025-11-19
categories: [RESEARCH]
tags: [DIGITSTEALER,MALWARE,MACOS,SECURITY,INFORMATION STEALER]
---

A new information stealer targeting macOS users, dubbed DigitStealer, has been identified. This malware employs advanced detection-evasion techniques and a multi-stage attack chain, presenting new challenges for Mac users.

DigitStealer distinguishes itself through platform-specific targeting, fileless operation, and anti-analysis techniques. The attack commences with a file disguised as a utility application called “DynamicLake,” hosted on a fraudulent website. Users are tricked into dragging a file into Terminal, which initiates the download and installation of DigitStealer. To evade analysis and avoid detection in its home country, the malware is programmed not to run on systems matching certain regions or virtual machines. Furthermore, it specifically targets devices with newer ARM features, such as those introduced with M2 chips or later, bypassing older Macs, Intel-based chips, and most virtual machines. The attack chain is predominantly fileless, minimizing traces left on affected machines. Unlike file-based attacks, this executes the payload in Random Access Memory (RAM), making it harder to detect and remediate.

DigitStealer's initial payload requests the user's password and attempts to steal documents, notes, and files, uploading them to the attackers' servers if successful. The second stage targets browser information from Chrome, Brave, Edge, Firefox, and others, along with keychain passwords, crypto wallets, VPN configurations (specifically OpenVPN and Tunnelblick), and Telegram sessions.

To protect against DigitStealer and similar threats, users are advised to employ an up-to-date real-time anti-malware solution capable of advanced behavioral protection, going beyond simple signature scans. It's crucial to exercise caution when executing commands in Terminal and avoid following instructions from unsolicited messages. Always download applications from trusted sources. Regularly update software, including the operating system and security defenses. Enabling multi-factor authentication can also prevent unauthorized access even if a password is stolen.

To read the complete article see: [Malwarebytes](https://www.malwarebytes.com/blog/news/2025/11/mac-users-warned-about-new-digitstealer-information-stealer)