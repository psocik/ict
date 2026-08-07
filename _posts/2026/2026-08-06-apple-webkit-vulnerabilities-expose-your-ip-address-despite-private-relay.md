---
title: Apple WebKit Vulnerabilities Expose Your IP Address Despite Private Relay
date: 2026-08-06
categories: [SECURITY]
tags: [APPLE,WEBKIT,PRIVACY,VULNERABILITIES]
---

## Apple WebKit Vulnerabilities Expose Your IP Address Despite Private Relay

🚨 **Three WebKit mechanisms have been discovered to bypass Apple's iCloud Private Relay!** This means that even with Private Relay, your IP address can still be exposed. 

### What is Private Relay?
Private Relay is a VPN-like system for Safari on iOS designed to prevent websites from viewing your IP address and location. However, researchers found that certain mechanisms can bypass this protection.

### The Three Vulnerabilities:
- **DNS Prefetching:** Modern browsers often look up the IP addresses of links on a page before you click them. In WebKit, these DNS lookups can bypass the configured proxy, exposing your DNS servers and location.
- **WebAuthn and Passkeys:** WebAuthn sometimes requires fetching a small file from the website's domain to verify credentials. This fetch occurs outside the usual WebKit page-loading path, revealing your true IP address.
- **WebTransport and Related Technologies:** This newer API allows websites to open low-latency connections to a server. In tested scenarios, these connections were initiated outside the proxied WebKit code path, exposing your real IP.

### User Experience Impact
All three mechanisms mimic normal browser behavior, making it easy for malicious sites to exploit them. Affected users include those on Safari for iOS and macOS when using Private Relay, as well as any browser or app relying on WebKit's proxy configuration.

The researchers have reported these issues to Apple and expect patches by fall. 

For more details, check out the full article: [Read full article](https://www.malwarebytes.com/blog/news/2026/08/apple-webkit-vulnerabilities-reveal-your-ip-address-despite-private-relay)