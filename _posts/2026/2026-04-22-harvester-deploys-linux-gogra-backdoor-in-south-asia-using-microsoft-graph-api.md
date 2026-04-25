---
title: Harvester Deploys Linux GoGra Backdoor in South Asia Using Microsoft Graph API
date: 2026-04-22
categories: [CYBERSECURITY]
tags: [LINUX,GOGRA,BACKDOOR,CYBERSECURITY,SOUTH ASIA]
---

## Harvester Deploys Linux GoGra Backdoor in South Asia Using Microsoft Graph API

The threat actor known as **Harvester** has been attributed to a new Linux version of its **GoGra backdoor** deployed as part of attacks likely targeting entities in South Asia. The malware uses the legitimate **Microsoft Graph API** and Outlook mailboxes as a covert command-and-control (C2) channel, allowing it to bypass traditional perimeter network defenses, the Symantec and Carbon Black Threat Hunter Team said in a report. The cybersecurity company identified artifacts uploaded to the **VirusTotal** platform from **India** and **Afghanistan**, suggesting that the two countries may be the target of the espionage activity.

Harvester was first publicly documented by Symantec in late 2021, linking it to an information-stealing campaign aimed at telecommunications, government, and information technology sectors in South Asia since June 2021, using a bespoke implant called **Graphon** that utilized the Microsoft Graph API for C2. Subsequent activity flagged in August 2024 connected the hacking group to an attack targeting an unnamed media organization in South Asia with a never-before-seen Go-based backdoor called **GoGra**. The latest findings suggest that the adversary is continuing to expand its toolset beyond Windows and infecting Linux machines with a new variant of the same backdoor.

The attacks employ social engineering to trick victims into opening **ELF binaries** disguised as PDF documents. The dropper then proceeds to display a lure document while stealthily running the backdoor. Like its Windows counterpart, the Linux version of GoGra abuses Microsoft's cloud infrastructure to contact a specific Outlook mailbox folder named **"Zomato Pizza"** every two seconds using **Open Data Protocol (OData)** queries. The backdoor scans the inbox for incoming email messages with a subject line starting with the word **"Input."** Once an email matching the criteria is received, it decrypts the Base64-encoded message body and executes it as shell commands using **"/bin/bash."** The results of the execution are sent back to the operator in an email message with the subject line **"Output."** After the exfiltration step is complete, the implant wipes the original tasking message to cover up the tracks.

**Symantec and Carbon Black** stated, "Despite using different deployment architectures and operating systems, the underlying C2 logic remains unchanged," adding that the teams "also identified several matching, hard-coded spelling errors across both platforms, which points towards the same developer being behind both tools." The use of a new Linux backdoor shows that Harvester is continuing to expand its toolset and actively develop new tooling in order to go after a wider range of victims and machines. 🚀

[Read full article](https://thehackernews.com/2026/04/harvester-deploys-linux-gogra-backdoor.html)