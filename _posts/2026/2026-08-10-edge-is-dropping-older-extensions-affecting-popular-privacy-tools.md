---
title: Edge is Dropping Older Extensions, Affecting Popular Privacy Tools
date: 2026-08-10
categories: [TECHNOLOGY]
tags: [MICROSOFT,EDGE,EXTENSIONS,PRIVACY,SECURITY]
---

## Microsoft Edge Extension Changes 🚀

Microsoft is beginning the retirement of **Manifest V2 (MV2)** extensions in Edge this month, with consumer completion targeted for the end of 2026 and managed-enterprise deprecation in early 2027. Microsoft states that this change is justified because **95%** of the most-used MV2 extensions in the Edge Add-ons store have already transitioned to **Manifest V3 (MV3)**. The company identified **58 MV2 extensions** with "meaningful usage," noting that only three lack a publicly available MV3 alternative.

Starting this month, some Edge users will see warnings in `edge://extensions` and on Edge Add-ons store pages. Over the following months, MV2 extensions will be disabled by default.

### Impact on Privacy Tools 🔒

This shift primarily affects privacy tools that modify requests, headers, redirects, or responses. MV2 extensions will need to be redesigned or risk losing specific features. Extensions relying on persistent background activity must also adapt to MV3's service worker lifecycle model. This change impacts several well-known privacy and content-blocking extensions, including the classic version of **uBlock Origin**, one of the most popular ad blockers for Edge, boasting over **13 million installs**.

### Security and Performance Improvements ⚡

The change aims to enhance security and performance. MV3 replaces some long-running background code and broad request-interception behavior with more constrained, declarative mechanisms. However, these constraints also eliminate capabilities that sophisticated privacy, content-blocking, and request-modifying extensions depended on. Several developers have expressed concerns about the challenges of adapting to MV3. One major issue highlighted is the limit on the number of rules a browser extension can include, as these rules must fit within browser-defined ceilings. For instance, Chrome documents a guaranteed minimum of **30,000 static rules**, a maximum of **100 declared static rulesets** with **50 enabled at once**, **5,000 session rules**, and limits on regular-expression rules.

The report clarifies that this does not mean Microsoft is banning ad blockers; rather, they simply need to find different ways to remain effective.

[Read full article](https://www.malwarebytes.com/blog/news/2026/08/edge-is-dropping-older-extensions-affecting-popular-privacy-tools)