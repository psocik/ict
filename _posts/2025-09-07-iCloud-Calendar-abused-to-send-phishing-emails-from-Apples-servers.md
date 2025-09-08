---
title: iCloud Calendar abused to send phishing emails from Apple’s servers
date: 2025-09-07
categories: [SECURITY]
tags: [ICLOUD,PHISHING,EMAIL SECURITY]
---

iCloud Calendar invites are being abused to send callback phishing emails disguised as purchase notifications directly from Apple's email servers, making them more likely to bypass spam filters to land in targets' inboxes.

The lure in this email is a typical callback phishing scam, but what was strange was that it was sent from noreply@email.apple.com, passing the SPF, DMARC, and DKIM email security checks, signifying that it legitimately came from Apple's mail server. 

As you can see from the above phishing email, this email is actually an iCloud Calendar invite, where the threat actor included the phishing text within the Notes field and then invited a Microsoft 365 email address that they controlled.

To read the complete article see:
[Full Article](https://www.bleepingcomputer.com/news/security/icloud-calendar-abused-to-send-phishing-emails-from-apples-servers/) 