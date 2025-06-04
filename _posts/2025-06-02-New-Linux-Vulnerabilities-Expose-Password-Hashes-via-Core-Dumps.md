---
title: New Linux Vulnerabilities Expose Password Hashes via Core Dumps
date: 2025-06-02
categories: [VULNERABILITIES]
tags: [LINUX,VULNERABILITIES,CORE DUMPS]
---

Two local information-disclosure vulnerabilities have been identified in popular Linux crash-reporting tools, allowing attackers to access sensitive system data.

The vulnerabilities, uncovered by the Qualys Threat Research Unit (TRU), impact Apport on Ubuntu and systemd-coredump on Red Hat Enterprise Linux (RHEL) and Fedora.

CVE-2025-5054 targets Apport, Ubuntu’s crash-reporting framework, while CVE-2025-4598 affects systemd-coredump, used on RHEL 9, RHEL 10 and Fedora 40/41.

Both are race-condition flaws that let local users exploit SUID programs to read core dumps from crashed processes.

To read the complete article see: [InfoSecurity Magazine](https://www.infosecurity-magazine.com/news/linux-vulnerabilities-expose/) 

Learn more here: [Qualys Blog](https://blog.qualys.com/vulnerabilities-threat-research/2025/05/29/qualys-tru-discovers-two-local-information-disclosure-vulnerabilities-in-apport-and-systemd-coredump-cve-2025-5054-and-cve-2025-4598) 
