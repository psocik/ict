---
title: Deadvax Threat Research Security Advisory
date: 2026-02-05
categories: [SECURITY]
tags: [MALWARE,THREAT RESEARCH,CYBERSECURITY,PHISHING]
---

## Deadvax Threat Research Security Advisory 🚨

**Source:** Securonix  
**Date Published:** February 5, 2026  

Securonix Threat Research has been tracking a stealthy malware campaign that utilizes an uncommon chain of VHD abuse, script-based execution, self-parsing batch logic, fileless PowerShell injections, and ultimately drops RAT. This research documents a real-world, multi-stage DeadVax campaign that exemplifies this evolution in attacker tradecraft. 

### Key Findings 🔍
- The infection chain begins with a phishing email delivering a Virtual Hard Disk (VHD) hosted on IPFS infrastructure.  
- The campaign uses IPFS-hosted VHD files disguised as business documents (DOCX/PDF) to bypass email gateway controls and reduce user suspicion.  
- The script-centric delivery chain flows through WSF, batch, and PowerShell scripts, complicating static detection.  
- The final malware stage is stored as noise-polluted Base64 data, decoded into raw shellcode and never written to disk in decrypted form.  

### Attack Details 📧
The attack begins with a phishing email impersonating Progressive Components (procoms.com). The attacker spoofs procoms.com via display name, but the actual sending domain is likely the compromised or malicious mingyitc.com. The email includes a fake “Virus scan completed. No threats detected” banner, and while it claims the attachment is a PDF, the downloaded file is actually a virtual hard disk .vhd container.  

After downloading, when a user tries to open this PDF-looking file, it mounts as a virtual hard drive. This technique is highly effective for evasion, as files inside the VHD do not inherit the mark of the web. The mounted drive contains a WSF script designed to trick the user into thinking it’s a PDF document.  

### Conclusion 📝
Dynamic analysis confirmed that the shellcode deploys a fully functional AsyncRAT implant. This advisory serves as a critical reminder of the evolving tactics used by cybercriminals and the importance of vigilance in cybersecurity practices.  

To read the complete article see: [Read full article](https://www.securonix.com/blog/deadvax-threat-research-security-advisory/)