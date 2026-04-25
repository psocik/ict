---
title: Russian APT28 Expands Arsenal with 'NotDoor' Outlook Backdoor
date: 2025-09-03
categories: [APT]
tags: [APT28,NOTDOOR,MALWARE,OUTLOOK]
---

The NotDoor backdoor is a sophisticated Visual Basic for Applications (VBA) based malware targeting Microsoft Outlook, designed to monitor incoming emails for specific trigger words and execute malicious commands.

Notably, the malware leverages DLL side-loading via a signed Microsoft binary (OneDrive.exe), which loads a malicious DLL (SSPICLI.dll) to deploy the backdoor while evading detection.

Triggered by emails containing a predefined string (e.g. "Daily Report"), NotDoor parses encrypted commands embedded in the message body, supporting multiple instructions per email, such as file theft, command execution, or additional payload downloads.

To read the complete article see:
[Infosecurity Magazine](https://www.infosecurity-magazine.com/news/russia-apt28-notdoor-outlook/) 