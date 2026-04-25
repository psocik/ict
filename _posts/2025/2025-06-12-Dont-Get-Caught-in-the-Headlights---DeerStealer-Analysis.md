---
title: Don't Get Caught in the Headlights - DeerStealer Analysis
date: 2025-06-12
categories: [SECURITY]
tags: [MALWARE,DEERSTEALER,HACKING,ESPIONAGE]
---

Throughout May 2025, eSentire's Threat Response Unit (TRU) detected several attempts by threat actors to download and execute HijackLoader. Many of these attempts involved the attempted deployment of DeerStealer AKA XFiles as the final payload, a sophisticated information stealer being sold on dark-web hacking forums by the user “LuciferXfiles”.

Key components in observed attack chains involve the use of the ClickFix initial access method, where victims are redirected to a phishing page prompting the user to execute a malicious command in the Windows Run Prompt. Immediately following is the download and execution of HijackLoader, a malware loader that first emerged in 2023 and is known for its use of steganography for storage of malware configuration settings and modules in an encrypted PNG image.

The final payload, known as “DeerStealer”, offers threat actors extensive capability to harvest cryptocurrency wallets, instant messengers, VPNs, and browser cookies, passwords, credit cards, and autofill from victim machines. The malware continues to evolve with planned features including MacOS support, AI integration, and automated crypto balance checking.

To read the complete article see: [Don't Get Caught in the Headlights - DeerStealer Analysis](https://www.esentire.com/blog/dont-get-caught-in-the-headlights-deerstealer-analysis).