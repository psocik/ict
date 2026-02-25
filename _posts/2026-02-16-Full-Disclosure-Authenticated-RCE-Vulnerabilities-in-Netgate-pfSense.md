---
title: Full Disclosure Authenticated RCE Vulnerabilities in Netgate pfSense
date: 2026-02-16
categories: [SECURITY]
tags: [CVE,RCE,NETGATE,PFSENSE,VULNERABILITY]
---

## Full Disclosure: CVE-2025-69690 & CVE-2025-69691

Two independent authenticated Remote Code Execution vulnerabilities were discovered in **Netgate pfSense Community Edition**. Both were reproduced on clean installations. The vendor was contacted and acknowledged the reports but classified both as expected behavior for authenticated administrators. This advisory is published in accordance with responsible disclosure practices. The vendor was notified on **December 2, 2025**, acknowledged the reports, and indicated no patches would be issued. Publication follows standard 90-day disclosure guidelines. CVEs: CVE-2025-69690 and CVE-2025-69691 were assigned by MITRE on **January 28, 2026**, with public disclosure occurring in **February 2026**.

### CVE-2025-69690
CVE-2025-69690, an Authenticated RCE via Unsafe Deserialization, affects pfSense CE 2.7.2 with a CVSS v3.1 score of **8.8 (High)**. The vulnerability is categorized under CWE-502: Deserialization of Untrusted Data and CWE-915: Improperly Controlled Dynamic Code Evaluation. The pfSense configuration restore mechanism invokes `unserialize()` on user-controlled data without class whitelisting, input validation, or sandboxing. A crafted backup file containing a malicious serialized PHP object can inject arbitrary commands via the `post_reboot_commands` property, executed through `mwexec()` with full root privileges. The attack vector involves an attacker authenticating as an administrator, uploading a malicious configuration backup file, triggering a restore operation, allowing pfSense to unserialize attacker-controlled data, and subsequently, commands execute as root via `mwexec()`. The impact includes arbitrary command execution as root, persistent compromise, complete firewall takeover, credential and configuration exfiltration. Netgate acknowledged the report and classified it as "authenticated administrative abuse," stating no patch would be issued.

### CVE-2025-69691
Additionally, CVE-2025-69691 identifies an Authenticated RCE via XMLRPC `exec_php` in pfSense CE 2.8.0, with a CVSS v3.1 score of **9.9 (Critical)**. This vulnerability is associated with CWE-284: Improper Access Control and CWE-915: Improperly Controlled Dynamic Code Evaluation. pfSense CE 2.8.0 exposes an XMLRPC API method `pfsense.exec_php` that executes arbitrary PHP code as root without validation, sandboxing, or restrictions. The endpoint is enabled by default, accessible over HTTPS via Basic Authentication, and executes supplied code immediately with full system privileges. Default credentials (`admin:pfsense`) are widely deployed, significantly lowering the exploitation barrier. The impact involves full remote root compromise, arbitrary file read/write, backdoor deployment, firewall rule manipulation, and extraction of secrets and configurations. Netgate acknowledged this report, classifying it as expected behavior for authenticated users, and indicated no patch in pfSense CE 2.8.0. The vulnerability is still exploitable as of the latest version at the time of disclosure.

For more details, check the full article: [Read full article](https://seclists.org/fulldisclosure/2026/Feb/16)