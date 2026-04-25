---
title: Patch and Persist Darktrace’s Detection of Blind Eagle (APT-C-36)
date: 2025-06-25
categories: [APT]
tags: [BLIND EAGLE,APT-C-36,DARKTRACE,CYBERSECURITY,PHISHING]
---

Since November 2024, Blind Eagle actors have been conducting an ongoing campaign targeting Colombian organizations. In this campaign, threat actors have been observed using phishing emails to deliver malicious URL links to targeted recipients, similar to the method previously used to exploit CVE-2024-43451, a vulnerability in Microsoft Windows that allows the disclosure of a user’s NTLMv2 password hash upon minimal interaction with a malicious file.

Despite Microsoft patching this vulnerability in November 2024, Blind Eagle actors have continued to exploit the minimal interaction mechanism, though without the intent of harvesting NTLMv2 password hashes. Instead, phishing emails are sent to targets containing a malicious URL, which, when clicked, initiates the download of a malicious file. This file is then triggered by minimal user interaction.

Clicking on the file activates a WebDAV request, establishing a connection over HTTP port 80 with the user agent ‘Microsoft-WebDAV-MiniRedir/10.0.19044’. WebDAV is a transmission protocol that allows files or complete directories to be made available through the internet and transmitted to devices. The next stage payload is then downloaded via another WebDAV request, executing malware on the target device.