---
title: Attackers are using “Sneaky 2FA” to create fake sign-in windows that look real
date: 2025-11-19
categories: [RESEARCH]
tags: [PHISHING,CYBERSECURITY,AUTHENTICATION]
---

A new phishing technique called Browser-in-the-Browser (BitB) is gaining traction, leveraging fake browser pop-up windows to steal credentials. This attack method presents a convincing fake login window directly within a webpage, making it difficult for users to distinguish from a legitimate sign-in prompt. A Phishing-as-a-Service (PhaaS) kit named Sneaky 2FA has emerged, providing attackers with the tools to easily deploy these deceptive attacks.

The Sneaky 2FA kit allows attackers to create fake browser windows using HTML and CSS, complete with a rendered address bar displaying the legitimate website's URL. This creates a highly deceptive illusion, as the window design, website address, and login form appear authentic. Attackers are also employing domain "burn and replace" tactics to evade blocklists, rapidly switching domains to maintain campaign effectiveness.

The BitB attack bypasses typical URL checks, as the fake URL bar mimics the real one. Password managers provide a strong defense, as they are designed to recognize only legitimate browser login forms and will not autofill credentials on these HTML fakes. Combining a password manager with multi-factor authentication (MFA) offers the best protection.

Sneaky 2FA employs evasion techniques, such as redirecting unwanted visitors to harmless sites and displaying the BitB page only to high-value targets. The pop-up window is also adapted to match each visitor’s operating system and browser. The use of obfuscated code also helps the attackers avoid detection and analysis.

Users should exercise caution and verify the legitimacy of any login prompt, even those that appear genuine. Avoid clicking links in unsolicited messages and stay informed about the latest phishing tactics. Browser extensions like Malwarebytes' Browser Guard can heuristically detect and block BitB attacks. Employing layered security measures is crucial to stopping attackers before they can compromise systems.

To read the complete article see: [Malwarebytes Blog](https://www.malwarebytes.com/blog/news/2025/11/attackers-are-using-sneaky-2fa-to-create-fake-sign-in-windows-that-look-real).