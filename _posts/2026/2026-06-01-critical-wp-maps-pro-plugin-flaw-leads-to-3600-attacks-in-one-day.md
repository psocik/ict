---
title: Critical WP Maps Pro Plugin Flaw Leads to 3,600 Attacks in One Day
date: 2026-06-01
categories: [SECURITY]
tags: [WORDPRESS,PLUGIN,VULNERABILITY,SECURITY]
---

## Critical Vulnerability in WP Maps Pro Plugin 🚨

Thousands of attacks were observed in a single day targeting a critical flaw in the **WP Maps Pro** plugin. Researchers disclosed this flaw, which allows attackers to create hardcoded admin accounts on WordPress sites. Exploitation is active, with Wordfence blocking over **3,600 attempts** in just one day. A patch was released on **May 20 (v6.1.1)**, and users must upgrade immediately to address this critical vulnerability.

Criminals are actively exploiting this vulnerability to take over entire websites. This alarming situation has been confirmed by multiple security researchers, including **David Brown**, who first disclosed the flaw, and **Defiant**, who reported in-the-wild exploitation attempts. The WP Maps Pro plugin is a premium tool used to create customizable maps and is currently utilized by more than **15,000 websites**.

According to Brown's research, the plugin suffers from a "privilege escalation via administrator account creation" vulnerability, allowing threat actors to create a new WordPress user with a hardcoded admin role. This vulnerability is tracked as **CVE-2026-8732** and carries a severity score of **9.8/10** (critical). It was found in versions **6.1.0** and older.

Defiant's researchers observed and stopped over **3,600 exploitation attempts** in just one day. They detailed the exploitation method, stating, "When the request is made with a check_temp parameter set to false, the function creates a new WordPress user via wp_insert_user() with the hardcoded role of administrator, a randomly generated username, and the hardcoded email address support@flippercode.com." They further explained, "The function then generates a 'magic login URL' using generate_login_link(), stores it as user meta, and returns it in the response body."

The fix was released just four days after the initial disclosure, on **May 20**. Users are advised to upgrade to version **6.1.1** as soon as possible to avoid being targeted. 

[Read full article](https://www.techradar.com/pro/security/wp-maps-pro-plugin-flaw-to-create-admin-accounts-on-wordpress-sites-saw-3-600-attempts-in-a-single-day)