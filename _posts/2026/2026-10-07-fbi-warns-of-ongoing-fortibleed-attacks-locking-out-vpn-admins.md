---
title: FBI Warns of Ongoing FortiBleed Attacks Locking Out VPN Admins
date: 2026-10-07
categories: [SECURITY]
tags: [FBI,FORTIBLEED,VPN,SECURITY,RANSOMWARE]
---

## FBI Warns of Ongoing FortiBleed Attacks Locking Out VPN Admins 🚨

The FBI is warning that **FortiBleed attacks** are still ongoing, targeting exposed Fortinet FortiGate firewalls and SSL VPN gateways, locking out legitimate administrators. Hackers gain access to exposed endpoints by using previously leaked credentials or logins obtained from infostealer logs, credential stuffing, and password spraying attacks. They then extract additional authentication data from compromised devices and use a distributed GPU cluster running Hashcat and Hashtopolis to crack offline the stolen password hashes. According to the FBI, "the FortiBleed attack chain has been observed as an initial entry point for ransomware affiliates." Some groups benefiting from this are **INC/Lynx ransomware** and **Payload ransomware**.

FortiBleed is a massive Fortinet credentials leak discovered in June, when attackers inadvertently exposed a server containing usernames and plaintext passwords associated with **73,932 firewall URLs** across **194 countries**. In July, SOCRadar linked FortiBleed to the INC and Lynx ransomware operations after getting access to both groups' negotiation panels on a server used in the campaign. By SOCRadar's latest count, the FortiBleed compromised **86,644 devices**.

The FBI says that in some incidents, the threat actor creates administrator accounts and uses their privileges to delete existing admin accounts or change their passwords, denying victims access to their devices. The attacker then establishes persistence and tries to move laterally in the environment. Details about the operation became known after the attacker accidentally exposed their backend server, revealing a directory with tooling and datasets. This showed the use of automated scripts to scan exposed FortiGate SSL VPN portals, a distributed GPU password-cracking setup, and scripts to validate credentials, filter out honeypots, identify organizations, and prioritize targets by revenue and network structure. Additionally, the exposure revealed working VPN configurations and target lists, indicating that the operator was packaging compromised access for sale.

The FBI warned that remediation may require more than patching and resetting Fortinet passwords, suggesting restricting external access, terminating all active VPN sessions, enforcing **MFA**, and reviewing logs for unauthorized changes and suspicious activity. They also recommend enforcing **PBKDF2** for administrator password storage, which is much stronger than legacy SHA-256 hashes that attackers can practically crack offline.

[Read full article](https://www.bleepingcomputer.com/news/security/fbi-ongoing-fortibleed-attacks-lock-out-fortigate-vpn-admins/) 
