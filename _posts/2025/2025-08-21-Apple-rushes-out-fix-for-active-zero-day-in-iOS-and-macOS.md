---
title: Apple rushes out fix for active zero-day in iOS and macOS
date: 2025-08-21
categories: [VULNS]
tags: [APPLE,IOS,MACOS,SECURITY]
---

Apple has shipped emergency updates to fix an actively exploited zero-day in its ImageIO framework, warning that the flaw has already been abused in targeted attacks.

Logged as CVE-2025-43300, the bug is an out-of-bounds write issue in ImageIO, the component apps rely on to read and write standard image formats. Apple warned that the flaw could let miscreants hijack devices with a booby-trapped image – and for some iDevice users, it sounds like the damage has already been done.

The company credits its own security team with the find and says it has tightened bounds checking to close the hole. Fixes landed on August 20 for iOS and iPadOS 18.6.2, macOS Sequoia 15.6.1, and the still-supported Sonoma 14.7.8 and Ventura 13.7.8, with a parallel update for older iPads on iPadOS 17.7.10.

[Read the complete article here](https://www.theregister.com/2025/08/21/apple_imageio_exploit/) 😃