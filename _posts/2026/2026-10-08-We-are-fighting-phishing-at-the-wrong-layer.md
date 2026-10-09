---
title: We are fighting phishing at the wrong layer
date: 2026-10-08
categories: [CYBERSECURITY]
tags: [PHISHING,CYBERSECURITY,SECURITY,ATTACKERS]
---

## We are fighting phishing at the wrong layer

**Source:** CSO Online  
**Date Published:** October 8, 2026  

Attackers can replace phishing domains almost for free, so security teams should hunt for the servers and infrastructure that are harder to hide. The domain is the cheapest thing the adversary owns, costing about a dollar and twenty minutes to replace. The layer where the attacker actually has costs is the server; find the server and you do not get one indicator, you get the estate. 

Modern phishing kits are adversary-in-the-middle proxies. Rather than serve a fake login page, they relay the victim's traffic to the real Microsoft sign-in service in real time, hand the real responses back, and harvest the credentials and the session token as they pass through. The victim sees a genuine page, completes a genuine multi-factor prompt, and the attacker walks away with a live session. Microsoft documented a single campaign of this shape that reached more than 10,000 organizations. 

These kits can disappear behind content delivery networks, with the origin dropping any connection that did not present the exact hostname it expected, without serving a byte. A null result from a scanning platform against a hostname-gated server does not mean nothing is there. Lures often arrive from genuinely compromised mailboxes, passing all authentication checks. 

What finally worked was a cookie the attacker's own server had handed to the victim. When the proxy relays a login, Microsoft sees a client connecting. That client is the proxy, and Microsoft sets a cookie recording the address it observed that client arriving from. The proxy then relays the response back down to the victim, cookie and all. So, the victim's browser receives a cookie stamped with the IP address of the attacker's own relay server. This value belonged to a small hosting reseller of the kind that takes cryptocurrency. 

This server-layer approach yields significant intelligence. The server address led to a second domain, which led in turn to a registrar the operator used nowhere else. Resolving the remaining domains grouped them onto a handful of machines. One reported phishing email became a mapped estate of dozens of lookalike domains impersonating real manufacturers, staffing agencies, and waste haulers, assembled patiently over six months to support invoice fraud against their customers. None of it was visible from the domain. All of it was visible from the server. 

If the proxy is what Microsoft sees, then the proxy is what your logs see. When one of your people is phished through one of these kits, the successful sign-in recorded in your tenant carries the relay's address, not your employee's. That is a detectable event, and it is one of the few reliable signals. Independent analysis has found that the large majority of accounts compromised through these kits already had multi-factor authentication enabled. 

Two things determine whether that detection actually works. The first is looking in hosting provider and virtual server ranges, because those are the networks your staff have no business signing in from and where these relays live. The second is remembering that the token is persistent, so the attacker's continued activity surfaces as refresh events rather than fresh sign-ins. A hunt that queries only interactive logins will find the moment of compromise and miss everything that came after it. 

When you do find one, the response order is not negotiable. Revoke the sessions first and reset the credential second. Reversed, you have accomplished nothing and the intruder keeps working while everyone believes the incident is closed.

[Read full article](https://www.csoonline.com/article/4231923/we-are-fighting-phishing-at-the-wrong-layer.html) 
