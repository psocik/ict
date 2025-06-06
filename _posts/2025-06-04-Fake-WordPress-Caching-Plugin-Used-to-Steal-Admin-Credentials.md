---
title: Fake WordPress Caching Plugin Used to Steal Admin Credentials
date: 2025-06-04
categories: [SECURITY]
tags: [MALWARE,WORDPRESS,SECURITY]
---

Identifying the malware

During a routine malware scan, we noticed a plugin labeled wp-runtime-cache in the wp-content/plugins directory. Seems innocent enough, right? After all, just about every site has at least one layer of cache to help with performance. When caching plugins are installed, you’ll usually find some menu to manage that at the top of the wp-admin panel or there will be some option under Settings on the left menu when logged in.

We did not see any options for clearing cache, and the plugin didn’t show up in the installed plugins list inside of wp-admin. It’s not uncommon for attackers to hide malicious plugins, so this definitely warranted further investigation.

Taking a look at the wp-runtime-cache directory, we could see one file: wp-runtime-cache.php. That’s also quite unusual since any valid plugin is going to utilize additional PHP and JS files for functionality. I mentioned we have seen a trend of utilizing malicious plugins, and in many cases, those malicious plugin directories only include one file containing the malicious code.

To read the complete article see: [Full Article](https://blog.sucuri.net/2025/06/fake-wordpress-caching-plugin-used-to-steal-admin-credentials.html)