---
title: Akira, LimeWire, and the Sour Taste of Data Exfiltration
date: 2026-06-12
categories: [CYBERSECURITY]
tags: [AKIRA,LIMEWIRE,DATA EXFILTRATION,RANSOMWARE,CYBERSECURITY]
---

## Akira, LimeWire, and the Sour Taste of Data Exfiltration

On May 29, the Huntress SOC detected unauthorized remote access to a domain controller within an organization. A closer inspection revealed that the threat actor accessed a hypervisor and created a new server instance, using this virtual machine to stage and launch the Akira ransomware. As this was a newly instantiated virtual machine, it lacked the security tools employed by the partner, including the Huntress agent.

One of the more intriguing aspects of this incident was the threat actor utilizing a file transfer function owned by LimeWire—a file-sharing client that many may have inadvertently infected their family computers with in the early 2000s—as a likely data exfiltration mechanism. 🚨

During the initial reporting, we detected enumeration activity, indicating that the threat actor used Notepad to open files (AdUsers.txt and AdComp.txt) and reviewed output files associated with enumerating Active Directory users and computers. They then pivoted to the organization's file server, employing several freely available tools. Notably, they used WinRAR, an archival tool seen in previous attacks, to archive the contents of a shared folder. Shortly after, they ran WinSCP, a free, open-source file manager and secure file transfer application, presumably to exfiltrate the staged data.

The creation of a new server instance from a hypervisor is not frequently observed by the Huntress SOC, nor is it commonly employed by ransomware affiliates, particularly those associated with Akira. The virtual machine's contents provided an insightful view into the threat actor's activity. For instance, the analysis showed that the threat actor accessed the new endpoint and, within minutes of logging in, disabled Microsoft Defender, the only default security tool in place. They accessed an archive containing various cross-platform versions of the Akira file encryptor executable before renaming one of those files to akira.exe.

Next, the threat actor used the Microsoft Edge browser to access Bing and searched for the term "eayupload" before settling on Easyupload.io, a website that allows file uploads via drag-and-drop. This site is supported by LimeWire, which has rebranded from a popular free peer-to-peer music downloading software to an NFT service and, more recently, a file-sharing platform. Shortly after accessing the LimeWire website, presumably to exfiltrate staged archives, the threat actor launched the akira.exe file encryptor against several mounted shares.

Another notable aspect of the VM analysis was how quickly the threat actor progressed through their attack. Aside from immediately disabling Microsoft Defender to launch the file encryptor unhindered, no other defense evasion or anti-forensics techniques were employed. The creation of the VM was clearly intentional, allowing the threat actor to bypass obstacles presented by the customer's security stack. 

For organizations, this incident underscores the necessity of monitoring environments for unusual or malicious access and watching for the addition or creation of new endpoints within the environment.

[Read full article](https://www.huntress.com/blog/akira-ransomware-limewire-data-exfiltration)