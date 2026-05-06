---
title: A Single 732-Byte Python Script Can Obtain Root on Linux Time to Update Your Kernel
date: 2026-05-05
categories: [CYBERSECURITY]
tags: [LINUX,VULNERABILITY,CYBERSECURITY,UPDATE]
---

## A Severe Vulnerability Alert 🚨

A severe vulnerability nicknamed **'Copy Fail'** allows a local user to dig into the guts of the OS and give themselves root privileges merely by writing four bytes of controlled data into the page cache of any readable file. The security research team at **Theori** disclosed the vulnerability last Wednesday. Additionally, **CISA** reports that threat actors have since been observed using the exploit in the wild. This security flaw has been designated as **CVE-2026-31431** and marked with a high severity score of **7.8** (via Bleeping Computer).

This is a critical issue because **Copy Fail** could potentially leave a large number of Linux users exposed. If you haven't updated your kernel in a while, now would be the time! Theori succinctly summarizes, "A single 732-byte Python script can be used to obtain root on essentially all Linux distributions shipped since 2017." Consequently, CISA added the vulnerability to its **Known Exploited Vulnerabilities Catalog**. In accordance with **'Binding Operational Directive (BOD) 22-01'**, this move requires Federal Civilian Executive Branch agencies throughout the USA to update their systems by **May 15** to protect against this active threat. CISA warns, "This type of vulnerability is a frequent attack vector for malicious cyber actors and poses significant risks to the federal enterprise."

Cybersecurity firm **Theori** also offers a more digestible **Copy Fail** guide. This guide includes the security research team's original Proof of Concept script so defenders can verify their own systems and validate vendor patches. It's worth clarifying that this script requires local access to a machine running Linux, and that the security vulnerability is not an example of remote code execution. The team found that the same script works in **Ubuntu 24.04 LTS**, **Amazon Linux 2023**, **RHEL 10.1**, and **SUSE 16**, with plenty of other Linux distros also affected.

For more details, check out the full article here: [Read full article](https://www.pcgamer.com/software/linux/a-single-732-byte-python-script-can-be-used-to-obtain-root-on-essentially-all-linux-distributions-shipped-since-2017-time-to-update-your-kernel/)