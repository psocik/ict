---
title: Fileless AsyncRAT Distributed Via Clickfix Technique Targeting German Speaking Users
date: 2025-06-16
categories: [CYBERSECURITY]
tags: [ASYNCRAT,MALWARE,CYBERSECURITY,CLICKFIX,GERMAN SPEAKING USERS]
---

**Executive Summary**

A fileless AsyncRAT joins the Clickfix party, with an obfuscated PowerShell-based campaign. The malware is delivered via a fake verification prompt that lures users into executing a malicious command. Based on the linguistic preferences in the verification prompt, we can ascertain with high confidence that the campaign is targeted towards German speaking users. The chain abuses legitimate system utilities and in-memory C# loaders with reversed strings to evade detection. Once executed, the malware establishes persistence through registry keys and connects to a remote TCP C2 server on port 4444. It enables full remote control, credential theft, and data exfiltration — all without dropping files to disk. Mitigations include blocking suspicious PowerShell execution, monitoring registry activity, and scanning memory for in-memory payloads commonly used in LOLBins-based delivery methods.

To read the complete article see:
[https://www.cloudsek.com/blog/fileless-asyncrat-distributed-via-clickfix-technique-targeting-german-speaking-users](https://www.cloudsek.com/blog/fileless-asyncrat-distributed-via-clickfix-technique-targeting-german-speaking-users)