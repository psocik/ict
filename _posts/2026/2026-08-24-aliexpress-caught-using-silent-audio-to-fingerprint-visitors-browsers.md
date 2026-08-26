---
title: AliExpress Caught Using Silent Audio to Fingerprint Visitors' Browsers
date: 2026-08-24
categories: [PRIVACY]
tags: [ALIEXPRESS,FINGERPRINTING,PRIVACY,TRACKING]
---

## AliExpress Caught Using Silent Audio to Fingerprint Visitors' Browsers

AliExpress, the online marketplace owned by Alibaba Group, has come under scrutiny after researchers and browser maker Brave reported finding silent Web Audio processing on the site that could help fingerprint visitors' devices. The audio processing did not record people through their microphones. Instead, it generated and processed an inaudible signal, then measured small, repeatable differences in the way a browser and device handled it. 

Browser fingerprinting is a way for websites to identify devices and recognize returning visitors without relying on conventional cookies. It works by using information about a device and browser to create a unique signature. 

The AliExpress website was found processing a fixed audio waveform and examining the resulting numerical values. Tiny differences can arise from the browser, operating system, CPU behavior, audio hardware, and drivers. When combined with other signals, they become another input that can contribute to a browser or device identifier. 

Investigation of the page's code reportedly found audio-processing graphs that were set to zero volume but remained connected to the system audio output. That explains why a user could hear nothing, and why muting a browser tab would not necessarily prevent the processing. All the relevant work was occurring within the Web Audio graph rather than through a conventional media player. Additionally, audio measurements were only one part of the reported data collection. The scripts also gathered information tied to canvas rendering, WebGL, display settings, hardware configuration, WebRTC behavior, and user interactions. Together, those signals can create a more detailed profile of a device than any one signal would provide on its own. 

Fingerprinting can be used for legitimate purposes such as fraud prevention, bot detection, and risk assessment. It can help companies spot suspicious transactions or automated activity even when cookies have been deleted or accounts have changed. However, it also raises privacy concerns because users may not know the tracking is happening and have limited control over it. Earlier studies have shown that visitors' choices about allowing cookies were ignored in more than half the cases studied. Fingerprinting adds another privacy concern because it can allow websites to recognize visitors without relying on cookies at all. 

The alleged AliExpress implementation is a useful example of how modern tracking can be both silent and technically legitimate at the API level while still raising privacy concerns. Brave says its browser blocks the AliExpress scripts responsible for the audio-based tracking. 

### What Can You Do?
- Use content blockers and anti-tracking extensions to limit the information websites can collect about your browser and device.
- Keep your browser up to date since browser vendors continually change privacy defenses as fingerprinting methods evolve.
- Use a separate browser or browser profile for shopping, ideally without signing in to other services in the same profile.

[Read full article](https://www.malwarebytes.com/blog/privacy/2026/08/aliexpress-caught-using-silent-audio-to-fingerprint-visitors-browsers)