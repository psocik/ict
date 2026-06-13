---
title: China-Linked Hackers Backdoored Linux Login Software to Hide for Nearly a Decade
date: 2026-06-12
categories: [CYBERSECURITY]
tags: [CHINA,HACKERS,LINUX,SECURITY,BACKDOOR]
---

## China-Linked Hackers Backdoored Linux Login Software to Hide for Nearly a Decade 🚨

A China-nexus group, known as Velvet Ant, has spent nearly a decade hiding within the Linux login system itself. Instead of lurking on laptops and servers that are closely monitored, they backdoored the PAM and OpenSSH components that control user sign-ins, embedding their access in a way that ordinary cleanup efforts cannot reach. The earliest traces of this activity date back to 2016.

Instead of deploying new malware that could be detected by scanners, the attackers modified the trusted login programs directly. This stealthy approach made their activities appear as normal administrative tasks, leaving no obvious signs of intrusion.

### Key Findings 🔍
- On many machines, the attackers replaced the main PAM login module with compromised versions, some allowing access via a secret password, while others recorded real usernames and passwords during logins.
- Researchers identified nine different versions of the backdoored software.
- The OpenSSH programs were similarly altered, capturing credentials and commands with a hidden switch to disable logging when necessary.

To infiltrate isolated networks, the attackers employed disguised tools and an internet-facing web server as a bridge, facilitating remote sessions deep within segments that lacked direct internet access. Because the login system itself was compromised, standard containment measures proved ineffective. Password resets and terminated sessions offered no protection when the credential-checking mechanism was under the attacker's control.

### Historical Context 📜
This is not the first time Velvet Ant has demonstrated such tactics. In a 2024 incident, they were found exploiting internet-exposed F5 BIG-IP appliances to establish internal command servers. Later that year, they exploited a Cisco NX-OS vulnerability (CVE-2024-20399) to plant a backdoor on switches, highlighting their persistent and adaptive nature.

### Recommendations 🛡️
- To mitigate risks, organizations should monitor PAM and OpenSSH programs and their key files for any unauthorized changes, and alert when modifications occur.
- Conduct hunts by checking what has changed rather than waiting for alerts. Compare these programs against known-good copies, as nothing will flag them for you.
- Remove any backdoors before resetting passwords to prevent new credentials from being compromised in the same manner. Always test replacements in a lab environment first.

The broader lesson is clear: infrastructure that exists outside of normal monitoring still requires integrity checks, including the login layer itself.

[Read full article](https://thehackernews.com/2026/06/china-linked-hackers-backdoored-linux.html)