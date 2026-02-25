---
title: Fake Incident Report Used in Phishing Campaign
date: 2026-02-17
categories: [CYBERSECURITY]
tags: [PHISHING,SECURITY,CRYPTO,METAMASK]
---

## Fake Incident Report Used in Phishing Campaign 🚨

An interesting phishing email was recently detected, offering insights into new **TTPs** ("tools, techniques & procedures"). This specific campaign targets users of **Metamask**, a popular software crypto wallet widely available as a browser extension and mobile app. The core of the phishing attempt is a request for the victim to enable **2FA** (Two-Factor Authentication). The email contains a link that directs users to an AWS server: [https://access-authority-2fa7abff0e.s3.us-east-1.amazonaws.com/index.html](https://access-authority-2fa7abff0e.s3.us-east-1.amazonaws.com/index.html).

In addition to the link, the phishing email includes an attached file titled **Security_Reports.pdf**. This PDF attachment contains a fake security incident report detailing unusual login activity. The primary goal of this elaborate setup is simple: to make the victim feel scared and consequently motivated to **increase** their security by enabling **2FA**. An analysis of the PDF content confirmed that it is not malicious. However, it is notable that the document was generated using **ReportLab**, an online service designed for creating PDF documents. ReportLab also provides a Python library for document creation. The SHA256 hash for this PDF file is `2486253ddc186e9f4a061670765ad0730c8945164a3fc83d7b22963950d6dcd1`.

Despite the idea to use a fake incident report, this campaign remains at a low quality level because the **From** address is not spoofed. Additionally, the PDF is not branded with at least the victim's email. If the creation of a PDF file can be automated, the report questions why it is not customized.

[Read full article](https://isc.sans.edu/forums/diary/Fake%20Incident%20Report%20Used%20in%20Phishing%20Campaign/32722/)