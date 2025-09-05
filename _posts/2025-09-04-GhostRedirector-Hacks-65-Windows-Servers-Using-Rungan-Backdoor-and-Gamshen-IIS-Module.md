---
title: GhostRedirector Hacks 65 Windows Servers Using Rungan Backdoor and Gamshen IIS Module
date: 2025-09-04
categories: [CYBERSECURITY]
tags: [MALWARE,CYBERSECURITY,WINDOWS SERVERS]
---

Cybersecurity researchers have lifted the lid on a previously undocumented threat cluster dubbed GhostRedirector that has managed to compromise at least 65 Windows servers primarily located in Brazil, Thailand, and Vietnam.

Rungan is designed to await incoming requests from a URL matching a predefined pattern (i.e., "https[:]//+:80/v1.0/8888[/]sys.html"), and then proceeds to parse and execute the commands embedded in them. It supports four different commands:

- **mkuser**: to create a user on the server with the username and password provided.
- **listfolder**: to collect information from a provided path (unfinished).
- **addurl**: to register new URLs that the backdoor can listen on.
- **cmd**: to run a command on the server using pipes and the CreateProcessA API.

Written in C/C++, Gamshen is an example of an IIS malware family called "Group 13," which can act both as a backdoor and conduct SEO fraud.

It's assessed with medium confidence that GhostRedirector is a China-aligned threat actor based on the presence of hard-coded Chinese strings in the source code, a code-signing certificate issued to a Chinese company, Shenzhen Diyuan Technology Co., Ltd., to sign the privilege escalation artifacts, and the use of the password "huang" for one of the GhostRedirector-created users on the compromised server.

To read the complete article visit: [The Hacker News](https://thehackernews.com/2025/09/ghostredirector-hacks-65-windows.html) 

---