---
title: New Android Pixnapping attack steals MFA codes pixel-by-pixel
date: 2025-10-14
categories: [SECURITY]
tags: [ANDROID,MFA,PIXNAPPING,SECURITY]
---

A new side-channel attack called Pixnapping enables a malicious Android app with no permissions to extract sensitive data by stealing pixels displayed by applications or websites and reconstructing them to derive the content.  

The attack starts with a malicious app abusing Android’s intents system to launch the target app or webpage, so its window is submitted to the system’s composition process (SurfaceFlinger), which is responsible for combining multiple windows when they are visible at the same time.  

Isolating each pixel is possible by opening what the researchers call a 'masking activity', which sits in the foreground, hiding the target app. Then the attacker makes the cover window 'all opaque white pixels except for the pixel at the attacker-chosen location which is set to be transparent.'  

Google attempted to fix the problem (CVE-2025-48561) in the September Android update. However, researchers were able to bypass the mitigation, and an effective solution is expected in the December 2025 Android security update.  

To read the complete article see: [Bleeping Computer](https://www.bleepingcomputer.com/news/security/new-android-pixnapping-attack-steals-mfa-codes-pixel-by-pixel/)  

Apply for our next conference in Kuala Lumpur on December 9th and 10th, 2025 at [Rise Malaysia](https://risemalaysia.eventify.io/p/#/overview) with the passcode: "6f&%dX", no quotes.