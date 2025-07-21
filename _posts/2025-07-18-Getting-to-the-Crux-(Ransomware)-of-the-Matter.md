---
title: Getting to the Crux (Ransomware) of the Matter
date: 2025-07-18
categories: [MALWARE]
tags: [RANSOMWARE,CRUX,CYBERSECURITY]
---

So far, we’ve seen the Crux ransomware being deployed in three separate incidents. Encrypted files end in the .crux file extension, and ransom notes follow the naming convention crux_readme_[random].txt. The support email address observed in all ransom notes thus far is BlackBCruxSupport@onionmail.org.

**Key takeaways:**  
Crux is a never-before-publicized variant that claims to be part of BlackByte ransomware.  
- One initial access vector used by the threat group appears to be via Remote Desktop Protocol (RDP).

Once the executable is launched, it has a distinctive process tree that progresses from the unsigned ransomware binary, through svchost.exe, cmd.exe, and bcdedit.exe, before encrypting files.

To read the complete article see: [Huntress Blog](https://www.huntress.com/blog/crux-ransomware).