---
title: HTTP Requests with X-Vercel-Set-Bypass-Cookie Header
date: 2026-04-28
categories: [RESEARCH]
tags: [HTTP,VERCEL,SECURITY,COOKIES]
---

## HTTP Requests with X-Vercel-Set-Bypass-Cookie Header

This weekend, we observed several requests to our honeypot that included an **X-Vercel-Set-Bypass-Cookie** header. Here’s a sample request:

```
GET / HTTP/1.1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/124.0.0.0 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate, br
Cache-Control: no-cache
Pragma: no-cache
Connection: keep-alive
X-Vercel-Set-Bypass-Cookie: samesite-none-secure
Upgrade-Insecure-Requests: 1
X-Forwarded-From: 21.235.92.139
X-Real-Iphone: 21.235.92.139
Referer: [redacted, same as "Host" header]
Host: [redacted]
```

Vercel documents the **x-vercel-protection-bypass** header (note: no "Cookie" part) as a secret that can be configured to disable certain protections during testing. This type of bypass feature is common across various platforms. In particular, web application firewall features often need to be disabled to allow higher request rates during CI/CD pipeline operations. The value set in the header is a user-configurable secret.

The **X-Vercel-Set-Bypass-Cookie** allows testing in browsers and maintains the bypass by having the server set a cookie to indicate the bypass. According to Vercel's documentation, there are two options: **True**, which enables the cookie; and **samesitenone**, which enables the cookie and sets the same-site property to none. However, I did not find the **samesite-none-secure** documented by Vercel. The most likely intention of the header is to relax security settings, potentially even exposing secrets, should Vercel reveal them in the cookie. I have not yet had the opportunity to test the request against a Vercel website.

The request was also routed through an open proxy, likely to protect the attacker's identity, but it failed due to the configured proxy headers.

To read the complete article see: [Read full article](https://isc.sans.edu/forums/diary/HTTP%20Requests%20with%20X-Vercel-Set-Bypass-Cookie%20Header/32930/)