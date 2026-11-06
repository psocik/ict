---
title: Hackers Hijack cPGuard Autoupdate to Deploy Backdoor and Steal Data
date: 2026-11-03
categories: [SECURITY]
tags: [HACKERS,CPGUARD,DATA-THEFT,SECURITY,MALWARE]
---

## Hackers Hijack cPGuard Autoupdate to Deploy Backdoor and Steal Data 🚨

Attackers have compromised the update infrastructure for the **cPGuard** web security suite to distribute a backdoor and a data-stealing script.

**OpsShield**, the cPGuard developer, published an alert earlier today saying the attack began on **November 2, 2026, at 02:06 UTC** and affected versions **5.88.12 through 5.88.19**. The vendor detected the compromise and stopped the malicious distribution within 12 hours after the attacker pushed the compromised cPGuard versions.

Although the company could not confirm, it said that some servers may not have received and run the malicious script due to update checks occurring at specific intervals. The attacker leveraged legitimate credentials to gain initial access, although it remains unclear how they were obtained.

> “On 2 November 2026 at 02:06 UTC, an unidentified attacker used compromised credentials to gain unauthorized access to OpsShield’s update distribution infrastructure (CDN),” OpsShield said.

The attacker used this access to distribute a malicious script through the cPGuard update channel. cPGuard is a Linux web-server security suite offering malware scanning, firewalls, and attack protection. It is commonly used by hosting firms and server administrators alongside panels such as **cPanel**, **DirectAdmin**, and **Plesk**. **Namecheap** offers it on VPS and dedicated servers.

### What Data Was Stolen? 📊

Users updating cPGuard during the compromise window received a script that targeted sensitive data on their machines:
- Linux password hashes
- Root database (MariaDB/MySQL) configuration
- Root shell history
- Root SSH authorization and known-hosts files

The stolen data was uploaded to OpsShield’s licensing server through a compromised account, which the attackers then used to retrieve it. While OpsShield has not established what data was collected from each server, the company's evidence from the investigation shows that the threat actor retrieved **32 files** from each customer.

### Recommendations for System Administrators 🔒

System administrators are advised to:
- Update every cPGuard server to version **5.88.25** or later
- Reset passwords
- Rotate database credentials, cloud secrets, and SSH keys

OpsShield notes that updating to the latest cPGuard version removes the backdoor and staged files; however, stolen credentials must be invalidated as soon as possible. The vendor also said that, as an extra precaution, it would release an update to remove previously installed OpsShield support-access keys.

BleepingComputer has contacted OpsShield to learn more about the attack, and a spokesperson told us that the incident has impacted nearly **three thousand servers**. 

> "We detected **2946 servers** were affected and copied the information mentioned, and our billing system database was copied over as well. We are working on blocking all access, rebuilding the affected systems, and preparing for a public announcement at the earliest possible time," the company representative said.

The company also advises customers to follow the instructions and update cPGuard to version **5.88.25** or later, and reset or rotate credentials that may have been exposed on potentially compromised servers.

[Read full article](https://bleepingcomputer.com/news/security/hackers-hijack-cpguard-autoupdate-to-deploy-backdoor-steal-data)