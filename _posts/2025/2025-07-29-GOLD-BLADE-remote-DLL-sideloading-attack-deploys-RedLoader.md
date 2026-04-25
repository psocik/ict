---
title: GOLD BLADE remote DLL sideloading attack deploys RedLoader
date: 2025-07-29
categories: [APT]
tags: [GOLD BLADE,REDLOADER,CYBERSECURITY,MALWARE]
---

Sophos analysts are investigating a new infection chain for the GOLD BLADE cybercriminal group’s custom RedLoader malware, which initiates command and control (C2) communications. The threat actors leverage a LNK file to remotely execute and sideload a benign executable, which loads the RedLoader stage 1 payload that is hosted on GOLD BLADE infrastructure. The threat actors previously used these techniques individually: the use of WebDAV to execute remotely hosted DLLs was observed in September 2024, and the sideloading of a renamed ADNotificationManager.exe file was observed in March 2025. However, the combination observed in July 2025 represents a method for initial execution that has not been publicly reported.

Execution chain: The attack starts with a threat actor sending a well-crafted cover letter PDF to a target via a third-party job site such as ‘indeed.com’. 

To read the complete article see: [GOLD BLADE remote DLL sideloading attack deploys RedLoader](https://news.sophos.com/en-us/2025/07/29/gold-blade-remote-dll-sideloading-attack-deploys-redloader/) 