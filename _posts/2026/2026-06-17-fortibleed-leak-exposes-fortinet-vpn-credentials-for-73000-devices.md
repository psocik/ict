---
title: FortiBleed Leak Exposes Fortinet VPN Credentials for 73,000 Devices
date: 2026-06-17
categories: [SECURITY]
tags: [FORTINET,VPN,DATA BREACH,CYBERSECURITY]
---

## FortiBleed Leak Exposes Fortinet VPN Credentials for 73,000 Devices 🚨

A newly discovered data leak dubbed **"FortiBleed"** has exposed what appears to be a collection of Fortinet and FortiGate VPN credentials for **73,932** firewall URLs at organizations worldwide. The exposed data was first discovered by security researcher **Bob Diachenko**, who found a server containing valid Fortinet VPN credentials, including usernames, email addresses, and plaintext passwords.

### Key Findings:
- The database contains entries for major organizations like **Chevron, Samsung, Foxconn, Comcast, AT&T, Mercedes-Benz,** and **Toyota**.
- Diachenko noted a **massive Fortinet/FortiGate bruteforce/active exploitation campaign** in action.
- The dataset includes comments listing each organization's industry, revenue, and number of employees, likely for planning attacks.

### Attack Details:
Diachenko later shared that the operation was conducted by a **Russian-speaking multi-operator threat group** that harvested credentials for FortiGate SSL VPN devices. The attackers allegedly conducted approximately **1.16 billion credential attempts** against **320,777** FortiGate targets and an additional **2.1 billion attempts** against **163,650 Microsoft SQL Server systems**.

### Impact:
According to threat intelligence company **Hudson Rock**, the dataset contains **73,932 unique firewall URLs** across **194 countries** and impacts **21,632 unique domains**. Organizations in the dataset should immediately rotate passwords associated with Fortinet VPN and administrative interfaces, enforce **MFA**, examine gateway logs for suspicious activity, and monitor for exposed employee credentials.

For more detailed information, please read the full article here: [Read full article](https://www.bleepingcomputer.com/news/security/fortibleed-leak-exposes-fortinet-vpn-credentials-for-73-000-devices/)