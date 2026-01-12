---
title: New MacSync Stealer Uses Signed macOS App to Evade Gatekeeper and Steal Data
date: 2026-01-10
categories: [CYBER SECURITY]
tags: [MACSYNC,MALWARE,CYBER SECURITY,MACOS]
---

Cybersecurity researchers have discovered a new variant of the MacSync malware targeting macOS users. Unlike previous versions that relied on complex ClickFix techniques, this iteration masquerades as a legitimately signed, notarised Apple application, thereby bypassing macOS Gatekeeper security and stealing sensitive data.

Jamf Threat Labs recently identified this evolved MacSync stealer, which includes two significant technical changes. The malware now presents itself as a code-signed and notarized Swift application, Apple’s official programming language for macOS development. This clever disguise helps the malware evade detection by appearing as a trusted app from a verified developer.

Cybercriminals obtain legitimate developer certificates through theft, the purchase of compromised developer accounts, or the establishment of fake developer companies using fraudulent identities. By leveraging these certificates, MacSync avoids triggering macOS security warnings about “unidentified developers” that would usually alert users to potential threats.

MacSync poses serious threats to infected systems. The malware can install backdoors for remote system control, steal stored data and browser information, target cryptocurrency wallet credentials, and maintain persistent hidden access. Jamf identified focusgroovy.com as a command-and-control server used to fetch additional payloads, with web browsers now flagging the site for suspected phishing activity, as reported by Moonlock.

To read the complete article see:
[Cyber Security News](https://cybersecuritynews.com/macsync-stealer-signed-macos-app-and-steal-data/)