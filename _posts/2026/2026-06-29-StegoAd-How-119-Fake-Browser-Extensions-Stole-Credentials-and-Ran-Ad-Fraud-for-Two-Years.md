---
title: StegoAd How 119 Fake Browser Extensions Stole Credentials and Ran Ad Fraud for Two Years
date: 2026-06-29
categories: [MALWARE]
tags: [MALWARE,BROWSER-EXTENSIONS,AD-FRAUD,CREDENTIALS-THEFT]
---

## StegoAd Campaign Exposed 🚨

Microsoft has successfully shut down the **StegoAd** campaign, which operated through **119 malicious Edge extensions**. This operation, which went undetected for **two years**, amassed approximately **2.6 million installs**. The report from Microsoft highlights the sophistication of this threat actor, describing it as one of the most technically advanced malicious browser extension campaigns encountered to date.

The extensions appeared completely normal, with the malicious payload activating days after installation. This delay allowed the campaign to evade multiple detection sweeps. The name **StegoAd** is derived from **steganography** and **ad injection**, the two main techniques used in this operation.

### Technical Details 🔍

The malicious actor cleverly hid executable JavaScript within PNG icon files, WebP images, and WOFF2 font files. This encoding technique disguised the JavaScript payload as high Unicode codepoints, making it appear as Asian text or font metadata to scanners. The extensions remained dormant for a period of **three to five and a half days** post-installation. If a user inspected the extension using DevTools, a flag called `dipFlgDev` was set, extending the dormancy period indefinitely.

The command-and-control (C2) server added another layer of complexity, only serving real payloads to requests that passed a fingerprint check based on the extension's runtime ID and the correct User-Agent.

### Ad Fraud and Credential Theft 💰🔑

The visible aspect of this campaign was ad fraud. The extensions injected ads, replacing existing Google AdSense and Amazon ad slots with the actor's own, hijacking affiliate commissions across various platforms, including eBay and AliExpress. Beneath this facade was a full remote code execution backdoor, allowing the C2 server to push arbitrary JavaScript to any victim's browser within **10 milliseconds**.

The credential theft module specifically targeted Google sign-in pages, capturing passwords and 2FA codes, sending them to `mitarchive.info` via double-Base64 encoding. A separate module also targeted WordPress admin login pages, attaching a SimilarWeb link to each stolen credential.

### Ongoing Threat 🚧

While Microsoft has not disclosed the identity of the threat actor, Koi Security has linked the credential exfiltration domain to **DarkSpectre**, a Chinese operation previously associated with other campaigns. The StegoAd campaign has shown remarkable adaptability, with the actor responding to detection efforts by shifting C2 domains and changing encryption schemes.

**Conclusion**: The StegoAd campaign illustrates a clear evolution in tactics over the past two years. Users are encouraged to upgrade their security measures, as hardware security keys provide better protection against this type of 2FA interception compared to SMS codes.

For more details, check out the full article: [Read full article](https://securityaffairs.com/194409/malware/stegoad-how-119-fake-browser-extensions-stole-credentials-and-ran-ad-fraud-for-two-years.html)