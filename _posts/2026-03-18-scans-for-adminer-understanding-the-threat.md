---
title: Scans for Adminer Understanding the Threat
date: 2026-03-18
categories: [SECURITY]
tags: [ADMINER,SECURITY,PHPMYADMIN,VULNERABILITIES]
---

## Scans for Adminer: Understanding the Threat

A very popular target of attackers scanning our honeypots is **phpMyAdmin**. phpMyAdmin is a script first released in the late 90s, before many security concepts had been discovered. Its rich history of vulnerabilities made it a favorite target. Its alternative, **Adminer**, began appearing about a decade later. Adminer is just a single PHP file. It requires no configuration. Users can copy it to their server, and they are ready to go. Adminer has a much better security record and claims to prioritize security in its development. 🚀  

Instead of using its own authentication or access control, Adminer simply asks the user to enter the SQL username and password they want to use to connect to the database. SQL databases have robust access controls, so there is no need to reinvent the wheel. Not having to store database credentials in a secrets file also removes several security headaches. But these credentials are, of course, still subject to brute-forcing. Adminer only allows 30 login attempts in 30 minutes. The main weakness likely represents users using weak passwords and relying on SQL authentication; there is no easy way to implement two-factor authentication. Adminer mitigates some of these issues with security plugins that implement OTP protection and other security features. 🔒  

This likely explains why attackers are scanning for Adminer, and they have been scanning quite aggressively lately. The increase in the number of URLs scanned is noteworthy. In phpMyAdmin scans, attackers often attempt to find obfuscated URLs used to host phpMyAdmin, such as "/pma/". For Adminer, attackers are scanning for different versions of the file. The filename released by Adminer includes the version number and the language or database type. For example, **adminer-5.4.2-mysql-en.php** is the English version for MySQL. 📈  

In short: Do not forget to read the security advice provided by Adminer, and you probably do not want to open Adminer to the internet. 🌐  

[Read full article](https://isc.sans.edu/forums/diary/Scans%20for%20%22adminer%22/32808/)