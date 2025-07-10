---
title: Animation-Driven Tapjacking on Android
date: 2025-07-08
categories: [MOBILE SECURITY]
tags: [ANDROID,TAPJACKING,CYBERSECURITY]
---

TapTrap is a new type of attack targeting Android devices. It allows an app without any permissions to misuse screen animations. This app can secretly open another screen, such as a permission prompt, and make it invisible. The attack can then be used to trick you into performing sensitive actions, such as granting camera permissions or even erasing your device, without your consent.

The idea is simple: imagine you’re using an app. While you use it, it opens another screen, such as a system prompt or simply another app. Normally, Android shows an animation when the screen changes, such as the new screen sliding or fading in. However, the app can tell the system that a custom animation should be used instead that is long-running and makes the new screen fully transparent, keeping it hidden from you. Any taps you make during this animation go to the hidden screen, not the visible app. The app can then use this to lure you into tapping on specific areas of the screen that correspond to sensitive actions on the hidden screen, allowing it to perform actions without your knowledge.

To read the complete article see: [TapTrap](https://taptrap.click/)