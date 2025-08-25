---
title: Malicious Go Module Poses as SSH Brute-Force Tool, Steals Credentials via Telegram Bot
date: 2025-08-24
categories: [RESEARCH]
tags: [CYBERSECURITY,MALWARE,SSH,TELEGRAM BOT]
---

Cybersecurity researchers have discovered a malicious Go module that presents itself as a brute-force tool for SSH but actually contains functionality to discreetly exfiltrate credentials to its creator.

"On the first successful login, the package sends the target IP address, username, and password to a hard-coded Telegram bot controlled by the threat actor," Socket researcher Kirill Boychenko said. The deceptive package, named "golang-random-ip-ssh-bruteforce," has been linked to a GitHub account called IllDieAnyway (G3TT), which is currently no longer accessible. However, it continues to be available on pkg.go[.]dev. It was published on June 24, 2022.



"The package offloads scanning and password guessing to unwitting operators, spreads risk across their IPs, and funnels the successes to a single threat actor-controlled Telegram bot," Boychenko said.

"It disables host key verification, drives high concurrency, and exits after the first valid login to prioritize quick capture. Because the Telegram Bot API uses HTTPS, the traffic looks like normal web requests and can slip past coarse egress controls."  

To read the complete article see:

[The Hacker News](https://thehackernews.com/2025/08/malicious-go-module-poses-as-ssh-brute.html) 