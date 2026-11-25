---
title: From Phishing Email To Azalea Agent Uncovering A Multi-Stage Attack On Ukrainian Government Bodies
date: 2026-11-24
categories: [CYBERSECURITY]
tags: [PHISHING,UKRAINE,CYBERATTACK,MALWARE,SECURITY]
---

## From Phishing Email To Azalea Agent: Uncovering A Multi-Stage Attack On Ukrainian Government Bodies

Seqrite Labs APT-Team recently analyzed a spear-phishing campaign targeting Ukrainian government bodies, observed on **October 13, 2026**. The campaign used a seemingly legitimate email lure related to financial assistance for a Ukrainian military unit. The email was sent from an account on the government domain **sm.gov.ua** to recipients on the Donetsk regional government domain **dn.gov.ua**, presented as a forwarded message related to the Ukrainian armed forces.

The email contained a RAR archive named **Лист від Сумської обласної Військової адміністрації до А1836 щодо перерозподіл субвенції трьох мільйонівна на нужди.rar**, which translates to "Letter from the Sumy Regional Military Administration to A1836 regarding the redistribution of a three-million subvention for needs". Inside the archive was a malicious LNK file that triggered a multi-stage infection chain.

Our analysis found that the infection chain eventually deploys **Azalea Agent 1.21.3**, a .NET-based remote access trojan. We have divided the technical analysis into five stages:

1. **Stage 1:** The infection begins with a malicious LNK file that uses the built-in curl utility to download the second-stage executable from the C2 server. This executable contains an encrypted overlay, which it processes to extract a DLL.
2. **Stage 2:** The DLL then decrypts the remaining data to produce the fourth-stage payload, a native loader identified as **NativeLoader**. NativeLoader reads its encrypted configuration, downloads the final payload, and loads it directly into memory using the .NET runtime.
3. **Stage 3:** The LNK file points to cmd.exe and contains a one-line command that uses the built-in curl utility to download a file from **https://151.244.30.176/194ff485-5d31-4a51-912e-b138e98ff750**. The downloaded file is saved as **rrfv01nekfc.exe** in the user's temporary directory and then executed in the background.
4. **Stage 4:** The executable that Stage 3 loads into memory calls itself **NativeLoader**. The loader looks for its configuration in an additional section named **.didat**. The configuration is obfuscated using two layers, applying a repeating 4-byte XOR key to recover the actual data.
5. **Stage 5:** The decoded configuration contains several settings, including a 4-byte XOR key, a 32-byte AES key, and a URL. We observed a call to **WinHttpCrackUrl** with the URL **https://151.244.30.176:80/505a3c0c-3cf2-4f5d-83b7-f6637ca3209f**. After downloading the payload, the loader decodes it in memory and executes its entry point.

This multi-stage attack highlights the evolving tactics used by cybercriminals and the importance of vigilance in cybersecurity practices. 🚀

[Read full article](https://www.seqrite.com/blog/from-phishing-email-to-azalea-agent-uncovering-a-multi-stage-attack-on-ukrainian-government-bodies/) 