---
title: User Agent Strings Curiosities
date: 2026-10-04
categories: [INFORMATION SECURITY]
tags: [USER AGENT,SECURITY,VULNERABILITIES,SCANNING]
---

## User Agent Strings Curiosities

Sometimes I have to smile, or my interest is triggered, when I review new User Agent Strings in the honeypot logs. Notable observations include instances like an **"authorized" scan**, or even **"I'm owned for the umpteenth time."** Furthermore, I regularly see URLs or email addresses for when you want to know more or get in touch with the persons behind a scanner. Many variants of masscan are observed, including a **KGB variant**. As you can guess, **"scan"** is a popular word to include in your UAS. Some wordplays are also thrown in, and scanners do not shy away from discrediting others.

Sometime complete lists of User Agent Strings are used: the scanner will select a new UAS for each request. However, they don't always sanitize these lists, as you can see with these weird **"User Agent Strings"**. These lines actually appear in this repository of User Agent Strings, to separate them in groups. As a result of a lack of quality control, these separator lines also get used as UAS in a request.

Of course, there are also attempts to exploit the parsing of a User Agent String. **Shellshock** may be more than 10 years old, but I still see it in User Agent Strings. This highlights continued scanning for known vulnerabilities. Additionally, researchers noted: **"Huh, are they scanning for this too?"** One such example is scanning for servers that stream GPS correction data via the **NTRIP protocol** (a NTRIP header was also included in this request).

[Read full article](https://isc.sans.edu/forums/diary/User%20Agent%20Strings%20Curiosities/33394/) 
