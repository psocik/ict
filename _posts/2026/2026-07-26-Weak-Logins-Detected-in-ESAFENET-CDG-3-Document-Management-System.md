---
title: Weak Logins Detected in ESAFENET CDG 3 Document Management System
date: 2026-07-26
categories: [SECURITY]
tags: [ESAFENET,DOCUMENT MANAGEMENT,SECURITY VULNERABILITIES,WEAK LOGINS]
---

## Weak Logins Detected in ESAFENET CDG 3 Document Management System

🚨 **Attention Security Professionals!** 🚨

Recent scans for the **ESAFENET CDG 3 Document Management System** have revealed weak logins, indicating a persistent threat actor interest. ESAFENET's CDG, which stands for **Content Data Guard**, has previously been flagged for security issues. This product, primarily targeting the Chinese market, is designed for secure document management and data leakage prevention. However, it is plagued by fundamental security vulnerabilities such as **SQL Injection**, **XSS**, and the use of **default passwords**.

### Current Threat Landscape

The ongoing scans are specifically targeting the well-known default passwords that come with the ESAFENET CDG. Exploit scripts that list these passwords have been included in a **nulei template** published in 2023.

### Example of Exploit Attempts

A notable example of this activity includes the following POST request:

```
POST /CDGServer3/SystemConfig
Host: [redacted]
User-Agent: Mozilla/5.0 (Ubuntu; Linux i686; rv:124.0) Gecko/20100101 Firefox/124.0
Content-Length: 73
Accept: */*
Accept-Language: en
Content-Type: application/x-www-form-urlencoded
Accept-Encoding: gzip
Connection: close
command=Login&help=null&verifyCodeDigit=dfd&name=secadmin&pass=Est@Spc820
```

This password, while appearing to meet many standard security checks (10 characters, upper/lower case, special characters, and numbers), is still highly insecure due to its status as a well-known default password.

For more detailed insights, check out the full article here: [Read full article](https://isc.sans.edu/forums/diary/Scans%20for%20ESAFENET%20CDG%203%20Document%20Management%20System%20Weak%20Logins/33184/)