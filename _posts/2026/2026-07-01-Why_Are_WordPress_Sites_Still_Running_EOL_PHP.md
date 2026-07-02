---
title: Why Are WordPress Sites Still Running EOL PHP?
date: 2026-07-01
categories: [WEB SECURITY]
tags: [WORDPRESS,PHP,SECURITY,VULNERABILITIES]
---

## Why Are WordPress Sites Still Running EOL PHP?  

Despite PHP updates being freely available, a large number of websites are not maintaining the latest patches, making them prime targets for attackers. 🚨 Within the population of publicly reachable WordPress instances observed in Censys, over **70%** were running outdated PHP versions. The most common PHP version observed overall was **PHP 7.4**, with over **20%** of sites still using it. PHP 7.4 reached its end of life in **November 2022**. By contrast, over **30%** of WordPress versions are on **6.9 or higher**, which are still actively maintained. This skew toward outdated versions represents a critical security concern for web servers. Not only are older frameworks less efficient, but they are also more susceptible to vulnerabilities. PHP upgrades are not optional improvements; they are critical security patches.  

The use of plugins for CMSes is also increasing. As of **June 2026**, nearly **7.5 million** WordPress sites have a listed plugin. Less than **22%** of sites advertising their Yoast versions are on the newest release (**27.7**, released **May 27, 2026**). This is a strong indicator that WordPress plugin patching is broadly deprioritized. Plugins present a unique challenge to secure in the sense that they are not monitored as extensively as WordPress core. For example, **UpdraftPlus**, a popular backup and migration WordPress plugin with over **3 million downloads**, has a high-risk profile if not maintained, with multiple CVEs that risk data exposure and authentication bypass. It's imperative for admins to keep track of plugin updates even for well-established plugins like UpdraftPlus, as every outdated plugin is its own potential entry point. Additionally, plugins can serve as an effective entry vector, and malicious actors can compromise popular plugins with a backdoor.  

Opportunistic bad actors frequently scan the web for misconfigured or unpatched WordPress sites, which are often treated as low-effort targets. One active example is the **"Hacked By MR.GREEN"** campaign: an unknown threat that defaces WordPress sites, replacing content and tagging 'MR.GREEN' in HTML page titles. As of **June 2026**, over **900 websites** were defaced with the message "Hacked by MR.GREEN", with nearly every victim being a CMS, the most common being WordPress. These defacements have been spotted as far back as **2020**. However, the campaign remains active today.  

While the exact access vectors behind MR.GREEN's campaign are unknown, the affected sites share a recognizable risk profile. Many show indications of outdated software and outward-facing misconfigurations, such as leaving `/wp-admin/install.php` exposed or using a default `xmlrpc.php` file as a way to remotely access the management console. WordPress's `xmlrpc.php` is a legacy API that enables remote procedure calls to the site. When left exposed, attackers can brute-force authentication and conduct plugin enumeration. GreyNoise sensor data shows **70 IPs** actively scanning for `xmlrpc.php` endpoints over the past **90 days**, indicating that this is a well-known misconfiguration that opportunistic actors routinely target. Additionally, many affected sites had misconfigurations in other services, such as exposed SSH ports with no IP restrictions and password authentication enabled.  

The MR.GREEN campaign highlights the importance of maintaining proper configurations and updates. Leaving CMS and backend platforms on default settings creates unnecessary exposure.  

[Read full article](https://censys.com/blog/wordpress-eol-php/)