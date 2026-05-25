---
title: From Edge Appliance to Enterprise Compromise Multi-Stage Linux Intrusion via F5 and Confluence
date: 2026-05-22
categories: [CYBERSECURITY]
tags: [LINUX,INTRUSION,CYBERSECURITY,F5,CONFLUENCE]
---

## Overview

A growing trend in modern intrusions is the compromise of internet-facing edge appliances such as firewalls and VPN gateways. Because these devices are externally exposed, lightly monitored, and highly trusted inside enterprise environments, compromise can provide a durable foothold with limited visibility. 🚀

In this incident, the threat actor compromised an internet-facing firewall appliance and used trusted relationships to pivot to an internal Linux host. From there, the threat actor compromised a vulnerable SaaS application and leveraged its credentials to conduct relay-style authentication attacks against Active Directory. The threat actor established SSH access to the first Linux host from a network device identified as an F5 BIG-IP load balancer. Device inventory confirmed the source as an Azure-hosted appliance running version 15.1.201000, which reached end-of-life (EOL) on December 31, 2024.

## Detailed Reconnaissance

The threat actor performed extensive reconnaissance of the host and network, including file enumeration, network scanning, and service discovery. They aggressively scanned the internal network subnets with Nmap to identify connected hosts, and then used Nmap on the identified hosts to detect open services. The threat actor used gowitness to perform a detailed reconnaissance of the HTTP/HTTPS services identified in the previous scan. Where they identified Windows servers, the threat actor tried common NTLM-based lateral movement techniques using open-source tools such as enum4linux, netexec, nmbclient, smbclient, rpcclient, timeroast, ldapsearch, kerbrute, nxc, and responder. These initial attempts were unsuccessful. 

The threat actor then downloaded a custom scanning tool from 206.189.27[.]39 using wget; this tool was detected as HackTool:Linux/MalPack.B.

## Exploitation of Vulnerabilities

During reconnaissance, the threat actor identified an Atlassian Confluence server within the network with unpatched vulnerabilities and leveraged these vulnerabilities to execute code remotely. After compromising the Confluence server, the threat actor obtained credentials and used them to attempt authentication against Windows infrastructure from files including /opt/atlassian/confluence/conf/server.xml and /var/atlassian/application-data/confluence/confluence.cfg.xml. This was followed by Kerberos relay attacks and exploitation of CVE-2025-33073, highlighting the risk of credential theft from internal web applications and the importance of monitoring cross-system authentication events. 

This incident vividly demonstrates that vulnerable applications don't need to be directly exposed to the internet to result in high severity compromises. Once an initial foothold is established, threat actors can pivot laterally and target internally accessible services to escalate privileges, expand access, or deploy tooling deeper into the environment. As a result, unpatched internal applications, particularly those running with elevated permissions or trusted identities, represent a critical attack surface and can materially impact the overall security posture of the environment.

## Mitigation Strategies

To mitigate such risks, organizations should treat internet-facing edge appliances as Tier-0 assets and enforce lifecycle + patch governance. In this intrusion, the initial foothold came from an end-of-life F5 BIG-IP version. Organizations should maintain an accurate inventory of externally exposed appliances, track end-of-support dates, and operationalize rapid patching for known-exploited vulnerabilities. Additionally, harden and patch internal web applications with the same urgency as internet-facing services. Critical internal applications (like Confluence) should be patched and monitored even if they have no direct internet exposure. Furthermore, apply identity hardening to reduce the feasibility and blast radius of relay-style authentication attacks. Defensive measures include minimizing or disabling NTLM where possible, enforcing SMB signing, enabling LDAP signing and channel binding, and using Extended Protection for Authentication (EPA) on applicable services to bind authentication to the channel and reduce relay success.

[Read full article](https://www.microsoft.com/en-us/security/blog/2026/05/22/from-edge-appliance-to-enterprise-compromise-multi-stage-linux-intrusion-via-f5-and-confluence/)