---
title: Hackers Breach F5 BIG-IP APM Devices to Deploy Linux Rootkit
date: 2026-09-08
categories: [SECURITY]
tags: [HACKERS,LINUX,ROOTKIT,F5,SECURITY]
---

## Hackers Breach F5 BIG-IP APM Devices to Deploy Linux Rootkit

A Linux rootkit targeting devices in F5 BIG-IP APM environments can intercept PHP file loading and inject a fileless web shell directly into memory, avoiding the need to write malicious code to disk. The malware shows signs of being a second-stage payload that was likely deployed after exploiting CVE-2025-53521, a critical remote code execution (RCE) flaw that F5 Networks reclassified from a DoS problem in March. **Sophos researchers** analyzed a sample and noted that, while it enables "on-demand server-side code execution" typically associated with webshells, it achieves this through **deeper Linux- and Apache-specific tradecraft**. 

During the research, Sophos learned that the same malware was analyzed by ESET, who identifies it as 'PoisonedRefresh.' 

In technical analysis published this week, Sophos says that the payload was deployed by a distinct installer or propagation component that had infected the Apache /usr/sbin/httpd executable used on BIG-IP APM systems. The malicious installer also modified SELinux configurations and achieved persistence across BIG-IP upgrade images, Sophos researchers say. The second-stage sample hides key operational strings with RC4, gains execution before the host application main() function is invoked by intercepting __libc_start_main, targets Apache's PHP module by hooking the Apache Portable Runtime (APR) module loader (apr_dso_load), and injects a PHP web shell into memory. 

The rootkit starts with Apache, with the second-stage implant intercepting PHP file operations and modifying them in memory to hide a web shell in legitimate scripts (e.g., apm_css.php3, full_wt.php3, and webtop_popup_css.php3). Sophos notes that the scripts were likely targeted because they are present in BIG-IP APM webtop environments and are less likely to trigger security alerts. Additionally, the PHP files on disk remain unchanged, significantly reducing the detection surface. The injected web shell accepts specially formatted ("magic") requests, decrypts their contents, executes them through PHP's eval() function, and returns an HTTP 201 response disguised as CSS content. 

Sophos highlights a protection mechanism that delays the creation of the local backdoor when Apache starts, reducing the risk of service disruption and detection. "When the Apache process begins making routine time calls, the implant spawns and detaches the worker thread responsible for creating the local UNIX socket backdoor," Sophos explains. The rootkit also creates a password-protected local communication socket that can launch an interactive Bash shell without opening a TCP listening port. The socket isn't directly exposed to the internet, so attackers would need another foothold on the device to access it; however, Sophos did not identify the component used to interact with it. 

The security firm shared a set of signals for malicious activity linked to the malware, which include Apache workers reading /proc/self/maps, changing libphp memory protections, creating /run/bigtlog.pipe, or launching /bin/bash. Defenders are also advised to investigate unusual POST requests to the targeted .php3 endpoints and PHP responses combining HTTP 201 with a text/css content type. The **ShadowServer Foundation**, which offers a tracker for F5 BIG-IP APM systems vulnerable to CVE-2025-53521, reports that 795 endpoints were exposed online yesterday.

To read the complete article see: [Read full article](https://www.bleepingcomputer.com/news/security/hackers-breach-f5-big-ip-apm-devices-to-deploy-linux-rootkit/) 
