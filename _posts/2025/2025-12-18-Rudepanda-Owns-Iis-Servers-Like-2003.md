---
title: Rudepanda Owns Iis Servers Like 2003
date: 2025-12-18
categories: [MALWARE]
tags: [IIS,ASP.NET,MALWARE,CYBERSECURITY]
---

The exploitability of application data which is stored on the client side (e.g., in a “viewstate”) has been thoroughly documented since 2010 for ASP.NET. However, exploiting the ASP.NET viewstate remains possible if secrets known as “machine keys” are known to attackers.

In early 2025, Microsoft alerted about the abuse of exposed ASP.NET machine keys to execute malicious code through viewstate manipulation, leading to the compromise of IIS servers. At the time of their publication, Microsoft had identified over 3,000 publicly exposed machine keys in code repositories or programming forums. During the summer of 2025, the exploitation of SharePoint vulnerabilities notably supported the exfiltration of ASP.NET machine keys, indicating that attackers maintain interest in viewstate exploitation.

The compromise of Microsoft IIS servers by financially motivated threat actors for Search Engine Optimization (SEO) fraud has been discussed by several vendors. In September last year, Cisco Talos described the activity of a threat actor they named DragonRank, who deploys IIS modules known as BadIIS to boost the visibility of specific websites. In recent weeks, several publications reported IIS server compromises for SEO poisoning, suggesting a growing prevalence of such activity.

Between late August and September this year, our product detected compromises of IIS web servers. Our investigation revealed that attackers first exploited the ASP.NET viewstate for remote code execution, then leveraged privilege escalation techniques known as “Potatoes” (EfsPotato and DeadPotato) to create an additional “hidden” local administrator (`admin$`). The attackers deployed a remote access tool (GotoHTTP) to interact with the graphical interface of compromised servers and ultimately deployed malicious IIS modules (later referred to as “HijackServer”). The threat actor relied on pre-packaged tools and scripts to partially automate the process and attempted to conceal the presence of deployed modules using a rootkit. The installation process included a noisy deletion of every single Windows Event log file, which contradicted attempts to conceal the modules.

Attackers exploited ASP.NET web applications to initially execute ASP payloads on targeted servers. The corresponding application logs showed multiple lines of suspicious POST requests when the first malicious activities were detected. The HTTP requests had various user agents (the client language was set to `zh-tw` when specified) and targeted the root pages (`/`) of applications.

To read the complete article see: [Harfanglab](https://harfanglab.io/insidethelab/rudepanda-owns-iis-servers-like-2003/).