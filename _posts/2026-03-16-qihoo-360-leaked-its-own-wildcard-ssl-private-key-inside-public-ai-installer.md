---
title: Qihoo 360 Leaked Its Own Wildcard SSL Private Key Inside Public AI Installer
date: 2026-03-16
categories: [CYBERSECURITY]
tags: [QIHOO,SSL,CYBERSECURITY,PRIVATE-KEY,AI]
---

## Qihoo 360 Leaked Its Own Wildcard SSL Private Key Inside Public AI Installer

China’s largest cybersecurity firm, **Qihoo 360**, has inadvertently exposed its own wildcard SSL private key by bundling it directly inside the public installer of its newly launched AI assistant, **360Qihoo (Security Claw)**. 🚨

Lukasz Olejnik, who downloaded the installer and inspected its directory structure, found a live, production-grade wildcard TLS private key sitting unprotected inside the package.

### Risks of Exposed SSL/TLS Private Key
An SSL/TLS private key is the cryptographic foundation of HTTPS. Possession of it allows an adversary to perform several high-impact attacks:
- **Man-in-the-Middle (MitM) interception** — silently decrypt all traffic between users and 360’s AI servers.
- **Server impersonation** — stand up a fake myclaw[. ]360[. ]cn endpoint that browsers trust as legitimate.
- **Credential harvesting** — serve convincing login pages that capture usernames and passwords.
- **AI session hijacking** — intercept or manipulate queries sent to the AI backend entirely.

To read the complete article see:
[Read full article](https://cybersecuritynews.com/qihoo-360-leaked-ssl-private-key/)