---
title: APT Group UAT-7237 Targets Taiwan's Web Infrastructure with Custom Tools
date: 2025-08-16
categories: [APT]
tags: [APT,TAIWAN,WEB INFRASTRUCTURE]
---

A Chinese-speaking advanced persistent threat (APT) group, tracked as UAT-7237, has been observed targeting web infrastructure entities in Taiwan using customized versions of open-sourced tools with an aim to establish long-term access within high-value victim environments.

Talos researchers observed the UAT-7237 APT group using a customized Shellcode loader tracked as "SoundBill." SoundBill can be employed to decode and load any shellcode, including Cobalt Strike.
UAT-7237 exploits unpatched servers for initial access, then performs rapid reconnaissance using commands like nslookup, systeminfo, and ping before establishing persistence via SoftEther VPN and RDP rather than web shells.
They move through networks using SMB shares and check for domain admins and controllers. They also use built-in Windows tools like SharpWMI and WMICmd to run commands, gather system info, and prepare for further attacks.

To read the complete article see: [Security Affairs](https://securityaffairs.com/181195/apt/taiwan-web-infrastructure-targeted-by-apt-uat-7237-with-custom-toolset.html).