---
title: Major password managers can leak logins in clickjacking attacks
date: 2025-08-20
categories: [SECURITY]
tags: [PASSWORD MANAGERS,SECURITY,CLICKJACKING]
---

The flaws were presented during the recent DEF CON 33 hacker conference by independent researcher Marek Tóth. Researchers at cybersecurity company Socket later verified the findings and helped inform impacted vendors and coordinate public disclosure. The researcher tested his attack on certain versions of 1Password, Bitwarden, Enpass, iCloud Passwords, LastPass, and LogMeOnce, finding that all their browser-based variants could leak sensitive info under certain scenarios.

Currently, the following password managers, which together have around 40 million users, are vulnerable to Tóth's attack methods:

- 1Password 8.11.4.27
- Bitwarden 2025.7.0
- Enpass 6.11.6 (partial fix implemented in 6.11.4.2)
- iCloud Passwords 3.1.25
- LastPass 4.146.3
- LogMeOnce 7.12.4

The vendors that implemented fixes are Dashlane (v6.2531.1 released on August 1), NordPass, ProtonPass, RoboForm, and Keeper (v17.2.0 released in July).

To read the complete article see: [Bleeping Computer](https://www.bleepingcomputer.com/news/security/major-password-managers-can-leak-logins-in-clickjacking-attacks/)  

👉 Stay informed and secure!