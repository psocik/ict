---
title: How a Plaintext File On Users’ Desktops Exposed Secrets Leads to Akira Ransomware Attacks
date: 2025-09-17
categories: [RESEARCH]
tags: [CYBERSECURITY,RANSOMWARE,AKIRA,ATTACK,VULNERABILITY]
---

A threat actor who gained initial access through a SonicWall VPN device was able to escalate their attack by finding Huntress recovery codes saved in a plaintext file on a user’s desktop. This allowed the attacker to log into the client’s security portal, where they attempted to remediate incident reports and uninstall security agents to cover their tracks.

SOC analyst Michael confirmed through event log analysis that the compromised user accounts were accessed from internal IP addresses in the 192.168.x.x range. These IPs were likely assigned via DHCP to systems controlled by the Akira threat actors after they compromised the organization’s SonicWall VPN. This technique allows attackers to blend in with legitimate network traffic, bypassing endpoint detection and response (EDR) solutions, as the rogue systems do not have security agents installed and their activity appears to originate from a trusted internal source.

During the investigation of the Domain Controller (DC), analysts observed the compromised user executing commands to list and export certificates from the local certificate store. The attacker specifically used commands to enumerate certificates in the personal store, which could contain sensitive keys for authentication, encryption, or signing. Subsequently, the attacker exported a certificate in PFX format, which includes both the public and private keys.

While enumerating administrative shares from the DC, the threat actor discovered and accessed a plaintext file on an internal security engineer’s desktop. These codes serve as a backup to bypass multi-factor authentication (MFA). Their compromise effectively grants an attacker full access to the Huntress console, allowing them to tamper with detection and response capabilities.

To read the complete article see: [Cybersecurity News](https://cybersecuritynews.com/plaintext-file-exposed-secrets/)  

---  

Working at Team Cymru is more than a job — it’s a chance to be part of something meaningful. Enjoy outstanding benefits, work with incredible people, and contribute to a mission that truly matters.  
Explore open roles and join us: [Team Cymru Careers](https://www.team-cymru.com/careers)