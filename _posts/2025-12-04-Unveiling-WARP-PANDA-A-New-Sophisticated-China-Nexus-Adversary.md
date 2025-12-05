---
title: Unveiling WARP PANDA A New Sophisticated China-Nexus Adversary
date: 2025-12-04
categories: [APT]
tags: [CHINA-NEXUS,WARP PANDA,CYBERSECURITY,THREAT INTELLIGENCE]
---

Using tradecraft focused on stealth and OPSEC, WARP PANDA leverages TTPs that include log clearing and file timestomping, as well as creating malicious VMs — unregistered in the vCenter server — and shutting them down after use. Similarly, in an attempt to blend in with legitimate network traffic, the adversary has used BRICKSTORM to tunnel traffic through vCenter servers, ESXi hosts, and guest VMs. BRICKSTORM implants masquerade as legitimate vCenter processes and have persistence mechanisms that allow the implants to survive after file deletion and system reboots.

In late summer 2025, the adversary exploited access to multiple entities’ Microsoft Azure environments, primarily to access Microsoft 365 data stored in OneDrive, SharePoint, and Exchange. In one instance, the adversary obtained user session tokens — likely by exfiltrating user browser files — and tunneled traffic through BRICKSTORM implants to access Microsoft 365 services via session replay. The adversary further accessed and downloaded sensitive SharePoint files related to an entity's network engineering and incident response teams.

In at least one case, to establish persistence, the adversary registered a new multifactor authentication (MFA) device via an Authenticator app code after initially logging into a user account. In another intrusion, the adversary used the Microsoft Graph API to enumerate service principles, applications, users, directory roles, and emails.

Active since at least 2022, WARP PANDA is a cloud-conscious targeted intrusion adversary that exhibits advanced technical skills and distinct malware use. To date, WARP PANDA is the only adversary that CrowdStrike Intelligence has observed leveraging BRICKSTORM, GuestConduit, and Junction; however, industry reporting has noted that BRICKSTORM is possibly leveraged by multiple adjacent China-nexus actors.

[Read the complete article here](https://www.crowdstrike.com/en-us/blog/warp-panda-cloud-threats/) .