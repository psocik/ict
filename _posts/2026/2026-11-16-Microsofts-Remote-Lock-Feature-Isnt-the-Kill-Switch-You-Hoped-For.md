---
title: Microsoft's Remote Lock Feature Isn't the Kill Switch You Hoped For
date: 2026-11-16
categories: [TECHNOLOGY]
tags: [MICROSOFT,REMOTE-LOCK,CYBERSECURITY,DATA-PROTECTION]
---

## Microsoft's Remote Lock Feature Isn't the Kill Switch You Hoped For

Microsoft is previewing a feature that allows administrators to remotely lock a stolen or compromised Windows device to preserve sensitive data. **"Windows signs out every active session, hides all sign-in options, and shows a locked screen. Nothing is erased, and the device stays enrolled and managed. BitLocker stays on, and user data stays in place,"** said Microsoft. Once the administrator has shut down the device, a **"DEVICE LOCKED"** message will appear on screen, and no amount of restarting will unlock it - only the administrator can.

This feature will be available on devices running Windows 11, Windows 10, Windows Server 2022, Windows Server 2019, and Windows Server 2016.

But experts say data can be accessed anyway. Microsoft Intune, a cloud-based administration portal designed for corporate IT and security teams, is a tool that could be easily exploited. While the feature may appear useful, there are situations where it could cause more harm than good, Cybernews information security researcher Rasa Jurgutytė said. **"One of them is when an attacker compromises an account that has permissions to lock or unlock other devices. This can be used to cause disruptions, e.g., if an attacker decides to lock 300 laptops simultaneously or lock the laptops of specific executives."**

Furthermore, Microsoft states that **"Boot and recovery paths are not blocked: Windows Recovery Environment, Safe Mode, and booting from USB or other media...keep BitLocker on to protect data if the drive is removed or the device is reimaged."** BitLocker does most of the work by encrypting files, preventing data theft. However, BitLocker isn't always on, meaning that thieves with physical access can bypass the lock through other recovery options. **"The device can be rebooted through recovery options, and the data that was there previously can be accessed anyway,"** said Jurgutytė.

The new remote lock feature may be a response from Microsoft following major cyberattacks that crippled some of its biggest customers. Stryker, a major global medical technology company with a total value of roughly $117.8 billion, was hit by hackers early this year. An Iranian-linked hacktivist group claimed responsibility for the breach, which allowed them to steal 50 terabytes of critical data. The medical tech giant's internal Microsoft environment was compromised, prompting an alert from US cybersecurity agency CISA. CISA warned of cyberattacks targeting endpoint systems and issued Microsoft Intune best practices to prevent further hacks.

[Read full article](https://cybernews.com/security/microsoft-remote-lock-bitlocker-reminder/)\n