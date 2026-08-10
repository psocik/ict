---
title: Hackers Breach TrueConf to Trojanize Client Installers with Backdoors
date: 2026-08-08
categories: [SECURITY]
tags: [HACKERS,TRUECONF,MALWARE,BACKDOORS,SECURITY]
---

## Hackers Breach TrueConf to Trojanize Client Installers with Backdoors 🚨

The Head Mare hacktivist group has been exploiting vulnerabilities in unpatched TrueConf video conferencing servers to replace client installers with malicious versions that deliver backdoors. The exploited vulnerabilities allowed the attacker to execute arbitrary code with the highest level of privileges and deploy the **PhantomCore** and **PhantomGraph** backdoors.

TrueConf is a video conferencing tool widely used in Russia, especially in the enterprise and government sectors. Kaspersky discovered the attack in July, noting that Head Mare hackers used TCP port 4307 to connect to the target TrueConf server without authentication. They leveraged a vulnerability internally tracked by Kaspersky as **KLCERT-26-057** to execute a malicious script within TrueConf's isolated environment, and **KLCERT-26-058** to escape the sandbox and run commands on the underlying operating system. The attacker then increased their privileges to **NT AUTHORITY\SYSTEM**, and replaced the `\public\js\locale.php` file with a web shell that gave them persistent remote access to the compromised server.

Kaspersky reports that Head Mare uses a web shell to collect sensitive information from the victim's environment, access the TrueConf database, and replace the legitimate TrueConf Client installer hosted on the server with a malicious version that contains the PhantomCore backdoor. When members of the organization connect to the local TrueConf server, they receive a trojanized, non-digitally signed client installer as an update. **Kaspersky warns**: "Even if your organization does not use the TrueConf server, employees can connect to compromised counterparty TrueConf servers to participate in online meetings and download infected installation packages."

Additionally, Head Mare deploys PhantomGraph, a separate backdoor consisting of two DLL files that accept commands via a Microsoft OneDrive account, execute them, and return the results. Observed attacker activity through PhantomGraph included dumping the memory of the Local Security Authority Subsystem Service (LSASS) process to exfiltrate credentials. The malware also runs commands for reconnaissance activity, such as hostname and whoami, and starts a reverse SSH tunnel.

Kaspersky is currently observing multiple active Head Mare campaigns targeting Russian organizations in various sectors. According to the researchers, the threat actor is using several initial access methods that include phishing, exploiting public-facing web servers, and access via contractors. The two flaws Kaspersky saw leveraged in attacks affect TrueConf Server versions 5.3.x before 5.3.9, 5.4.x before 5.4.9, 5.5.x before 5.5.5, and older versions. The vendor fixed them in versions 5.3.9, 5.4.9, and 5.5.5, released on June 18.

[Read full article](https://www.bleepingcomputer.com/news/security/hackers-breach-trueconf-to-trojanize-client-installers-with-backdoors/)