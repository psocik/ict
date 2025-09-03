---
title: Iran-Nexus Hackers Abuses Omani Mailbox to Target Global Governments
date: 2025-09-02
categories: [CYBERSECURITY]
tags: [APT,IRAN,CYBERSECURITY,MALWARE]
---

A sophisticated spear-phishing campaign orchestrated by Iranian-aligned operators has been identified targeting diplomatic missions worldwide through a compromised Ministry of Foreign Affairs of Oman mailbox. The campaign leveraged social engineering techniques to distribute malicious Microsoft Word documents masquerading as urgent diplomatic communications. 

Attackers sent emails from a compromised @fm.gov.om address, routing traffic through a NordVPN exit node in Jordan (212.32.83.11) to obscure their true origin.

The malware embedded within attached Word documents employed sophisticated encoding techniques, converting numerical sequences into ASCII characters through VBA macro code execution. The malicious documents contained VBA macros hidden within "This Document" and "UserForm1" modules, implementing a multi-stage payload delivery system. The primary decoder function, designated as "dddd," systematically processes encoded strings by reading three-digit segments and converting them to ASCII characters.

A particularly noteworthy evasion technique involves the "laylay" function, which creates artificial delays through four nested loops executing 105 iterations each. This anti-analysis routine significantly hampers dynamic analysis tools and automated sandbox detection systems. The malware writes its payload to C:\Users\Public\Documents\ManagerProc[.]log, disguising the executable as a harmless log file before execution via the Shell command with vbHide parameters. Upon successful deployment, the sysProcUpdate executable establishes persistence by copying itself to C:\ProgramData\sysProcUpdate[.]exe and modifying Windows registry DNS parameters. The malware collects system metadata including username, computer name, and administrative privileges, transmitting this information via encrypted HTTPS POST requests to the command-and-control server at screenai[.]online/Home/. 

To read the complete article see: [Cybersecurity News](https://cybersecuritynews.com/iran-nexus-hackers-abuses-omani-mailbox/) 

🚀 Stay informed on the latest cybersecurity threats!