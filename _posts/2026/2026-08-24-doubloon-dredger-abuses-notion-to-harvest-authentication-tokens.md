---
title: Doubloon Dredger Abuses Notion to Harvest Authentication Tokens
date: 2026-08-24
categories: [CYBERSECURITY]
tags: [DOUBLOON DREDGER,NOTION,PHISHING,AUTHENTICATION TOKENS,CYBERSECURITY]
---

## Doubloon Dredger Abuses Notion to Harvest Authentication Tokens 🚨

A financially motivated threat actor, known as **Doubloon Dredger**, has been observed exploiting free Notion accounts, malicious PDFs, and device code phishing to harvest authentication tokens from targeted organizations. Sublime's Threat Intelligence & Research team identified this activity in **July 2026** after a customer reported abuse of Notion, a digital workspace and collaboration application. Researchers found similar attacks against another organization.

The campaigns utilized fake accounts impersonating senior executives to send document-sharing notifications from legitimate Notion infrastructure. The emails informed recipients that an executive at their company had shared a document with them. Since these notifications were generated through compromised Notion accounts, they successfully passed DKIM, SPF, and DMARC checks.

Clicking the notification led the recipient to an intermediary PDF. A "Review and Sign" button then redirected the victim to an **EvilTokens** device code harvesting page disguised as an Adobe Acrobat document-sharing authentication screen. This page provided a verification code and instructions directing the victim to Microsoft's legitimate login or device code entry page. If the victim entered the code, EvilTokens could obtain an authorization token, granting the attacker access to the account. The platform also offers **MailVault**, a webmail client that allows attackers to interact with compromised inboxes.

EvilTokens has been available as a phishing-as-a-service (PaaS) platform since at least **February 2026**, with access sold through a private Telegram channel, according to Sublime.

Sublime identified **14 additional PDFs** with the same metadata and overlapping link construction. Each PDF contained two or three links placed over the same button, meaning different PDF readers could present different destinations. The PDFs targeted organizations across manufacturing, telecommunications, retail, health, and logistics, while some samples linked to **Kratos** phishing pages rather than EvilTokens. Researchers also found similarities between the campaign's first-stage JavaScript and **Tycoon2FA** device code harvesting activity. Their analysis identified **603 related scripts**, with **416** decoding to EvilTokens and **187** to Tycoon2FA. Sublime assessed with moderate confidence that Doubloon Dredger was a customer of both PhaaS platforms.

These findings come months after a global operation disrupted Tycoon2FA, although the platform resumed activity shortly afterward.

Sublime recommended organizations disable device code authentication where possible or restrict device code token generation to trusted devices.

[Read full article](https://www.infosecurity-magazine.com/news/doubloon-dredger-notion/)