---
title: Credential-Stealing Crew Spoofs VPN Clients from Cisco, Fortinet, and Others
date: 2026-03-13
categories: [CYBERSECURITY]
tags: [MALWARE,VPN,CYBERCRIME,CREDENTIALS]
---

## Credential-Stealing Crew Spoofs VPN Clients 🚨

A group of cybercriminals tracked as **Storm-2561** is using fake enterprise VPN clients from **CheckPoint**, **Cisco**, **Fortinet**, **Ivanti**, and other vendors to steal users' credentials, according to Microsoft. Storm-2561 is a relatively new criminal gang that has been around since **May 2025** and typically uses SEO positioning and vendor impersonation to distribute malware. This campaign, which started in **mid-January**, is no different.

The crew gains initial access to victims by manipulating search results and pushes malicious websites masquerading as enterprise VPN updates to the top of the list. So when a user searches for a VPN client such as "Pulse VPN download" or "Pulse Secure client," the top results point to a spoofed website mimicking the real vendor's page. These include products from **SonicWall**, **Sophos**, and **WatchGuard**, in addition to the VPN vendors listed above. Clicking on the link redirects users to a malicious GitHub repository that hosts the fake VPN clients disguised as **Microsoft Windows Installer (MSI)** files. Microsoft has observed spoofing of various VPN software brands and has noted the GitHub link at the following two domains: **vpn-fortinet.com** and **ivanti-vpn.org**. The GitHub repositories have since been taken down.

The installer sideloads malicious dynamic link library (DLL) files, **dwmapi.dll** and **inspector.dll**, during installation, and the phony VPN software prompts the user to enter their credentials. This captures the usernames and passwords, sending them to an attacker-controlled command-and-control server, all while appearing to be a legitimate client application. The MSI file and malicious DLLs are signed with a valid - and now revoked - digital certificate from **Taiyuan Lihua Near Information Technology Co., Ltd.** Immediately after a user enters their credentials into the fake sign-in page, the application displays an error message saying the installation failed, and then instructs the victim to download the legitimate VPN client from the vendor's official website. If users successfully install and use legitimate VPN software afterward, and the VPN connection works as expected, there are no indications of compromise to the end user. Users are likely to attribute the initial installation failure to technical issues, not malware.

To prevent credential theft, enforce **multi-factor authentication (MFA)** on all accounts. Make sure to remove users excluded from MFA, and require MFA from all devices, everywhere, at all times. Additionally, remind employees **NOT** to store workplace credentials in browsers or password vaults secured with personal credentials.

[Read full article](https://www.theregister.com/2026/03/13/vpn_clients_spoofed/)