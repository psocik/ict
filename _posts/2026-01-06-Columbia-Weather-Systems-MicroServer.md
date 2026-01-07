---
title: Columbia Weather Systems MicroServer
date: 2026-01-06
categories: [VULNERABILITIES]
tags: [CVE-2025-61939,CVE-2025-64305,CVE-2025-66620,CRITICAL INFRASTRUCTURE,INFORMATION TECHNOLOGY]
---

Successful exploitation of these vulnerabilities could allow an attacker to redirect connections to an attacker-controlled device, gain admin access to the web portal, or gain limited shell access. The following versions of Columbia Weather Systems MicroServer are affected: MicroServer firmware (CVE-2025-61939, CVE-2025-64305, CVE-2025-66620). Columbia Weather Systems MicroServer firmware versions less than MS_4.1_14142 are known to be affected. These systems are relevant to Critical Infrastructure Sectors: Information Technology, and are deployed in the United States.

Specifically, CVE-2025-61939 involves an unused function in the MicroServer that can start a reverse SSH connection to a vendor registered domain, without mutual authentication. An attacker on the local network with admin access to the web server, and the ability to manipulate DNS responses, can redirect the SSH connection to an attacker-controlled device. Additionally, CVE-2025-64305 highlights that the MicroServer copies parts of the system firmware to an unencrypted external SD card on boot, which contains user and vendor secrets. An attacker can utilize these plaintext secrets to modify the vendor firmware or gain admin access to the web portal.

Furthermore, CVE-2025-66620 concerns an unused webshell in the MicroServer that allows unlimited login attempts, with sudo rights on certain files and directories. An attacker with admin access to the MicroServer can gain limited shell access, enabling persistence through reverse shells, and the ability to modify or remove data stored in the file system. UsrPacific/Columbia Weather Systems reported these vulnerabilities to CISA. Columbia Weather Systems recommends users update the MicroServer firmware to version MS_4.1_14142 or later.

CISA recommends users take defensive measures to minimize the risk of exploitation of these vulnerabilities, such as minimizing network exposure for all control system devices and/or systems, ensuring they are not accessible from the internet. They also advise locating control system networks and remote devices behind firewalls and isolating them from business networks. When remote access is required, CISA recommends using more secure methods, such as Virtual Private Networks (VPNs), recognizing VPNs may have vulnerabilities and should be updated to the most current version available. CISA reminds organizations to perform proper impact analysis and risk assessment prior to deploying defensive measures. No known public exploitation specifically targeting these vulnerabilities has been reported to CISA at this time.

To read the complete article see:
[Full Article](https://www.cisa.gov/news-events/ics-advisories/icsa-26-006-01) ➡️