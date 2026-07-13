---
title: Researcher Finds 9 Vulnerabilities in ATM Security Software
date: 2026-07-10
categories: [SECURITY]
tags: [ATM,VULNERABILITIES,SECURITY,ENCRYPTION]
---

## Researcher Finds 9 Vulnerabilities in ATM Security Software

According to coverage from Dark Reading, a researcher has discovered nine vulnerabilities in the **CryptWare CryptoPro Secure Disk** software, which is a full-disk encryption solution used in corporate environments and by ATM manufacturers. While the existence of these vulnerabilities is not disputed, there is disagreement between the researcher and Diebold Nixdorf, a major ATM manufacturer, regarding their potential impact on the ability to steal cash from ATMs.

The researcher, **Matt Burch**, a principal security researcher at Atredis Partners, will present his detailed findings on CryptoPro Secure Disk at **Black Hat USA 2026**. These vulnerabilities primarily lie in how the software handles pre-boot decryption and stores its own sensitive information. Specifically, Burch found that in certain fail states, the software could mount volumes in plaintext. Furthermore, key material and configuration values were stored on the disk itself. This specific issue, combined with a superficial check for LUKS encryption, could allow an attacker to trick the system into mounting the disk in plaintext. Additionally, the software's Secure Boot setup could allow an attacker to run an arbitrary Linux environment on an ATM. Burch demonstrated that these identified issues could allow an attacker to execute their own code during pre-boot, recover decryption keys, and potentially steal cash using jackpotting techniques. 🚀

However, Diebold Nixdorf has stated that the findings are not directly applicable to their systems, though they acknowledge using some components of CryptoPro in their Vynamic Security Suite. They maintain that the vulnerabilities pose little to no additional risk to their ATMs in a real-world environment, although they conceded that two vulnerabilities are theoretically applicable under certain conditions. Diebold appears to have addressed these specific issues in a December 2025 update. CryptoPro Secure Disk is used by numerous organizations globally, highlighting the importance of securing cryptographic secrets.

[Read full article](https://www.scmagazine.com/brief/researcher-finds-nine-vulnerabilities-in-atm-security-software)