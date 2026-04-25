---
title: King Addons flaw lets anyone become WordPress admin
date: 2025-12-03
categories: [SECURITY]
tags: [WORDPRESS,VULNERABILITY,CVE-2025-8489,KING ADDONS,ADMINISTRATIVE PRIVILEGE]
---

Hackers are exploiting a critical vulnerability, tracked as CVE-2025-8489 (CVSS score of 9.8), in the WordPress plugin King Addons for Elementor that allows unauthenticated users to create admin accounts via a registration privilege bug.

The vulnerability in King Addons for Elementor lies in the `handle_register_ajax()` function. Attackers can send a crafted request to `/wp-admin/admin-ajax.php` specifying the `administrator` role, granting themselves full admin privileges. Exploiting this flaw lets them take control of the site, upload malicious code, distribute malware, redirect visitors to malicious sites, or inject spam.

“As with any Privilege Escalation vulnerability, this vulnerability can be used for a complete site compromise. Once an attacker has gained administrative user access to a WordPress site, they can then manipulate anything on the targeted site as a normal administrator would. This includes the ability to upload plugin and theme files, which can be malicious zip files containing backdoors. Additionally, they could modify posts and pages which can be leveraged to redirect site users to other malicious sites or inject spam content.”

Since the King Addons for Elementor vulnerability was disclosed, Wordfence has blocked over 48,400 exploit attempts. Exploitation attempts began on October 31, and the researchers observed spikes on November 9–10. Top attacking IPs include 45.61.157.120 (≈28,900 blocks) and 2602:fa59:3:424::1 (≈16,900 blocks). Indicators of compromise include new malicious admin accounts and suspicious requests from these IPs. A thorough review is recommended if abnormal activity appears, even if no logs show attacks.

To read the complete article see: [Security Affairs](https://securityaffairs.com/185286/hacking/king-addons-flaw-lets-anyone-become-wordpress-admin.html).