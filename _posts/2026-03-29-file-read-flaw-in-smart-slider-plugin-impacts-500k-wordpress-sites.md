---
title: File Read Flaw in Smart Slider Plugin Impacts 500K WordPress Sites
date: 2026-03-29
categories: [SECURITY]
tags: [WORDPRESS,VULNERABILITY,PLUGIN,SMART-SLIDER]
---

## 🚨 Vulnerability Alert: Smart Slider Plugin

A vulnerability in the **Smart Slider 3** WordPress plugin, active on more than **800,000 websites**, can be exploited to allow subscriber-level users access to arbitrary files on the server. An authenticated attacker could use it to access sensitive files, such as `wp-config.php`, which includes database credentials, keys, and salt data, creating the risk for user data theft and complete website takeover.

Smart Slider 3 is one of the most popular WordPress plugins for creating and managing image sliders and content carousels. It offers an easy-to-use drag-and-drop editor and a rich set of templates to choose from.

On **February 23**, Ignatyev reported his findings to Wordfence, whose researchers validated the provided proof-of-concept exploit and informed Nextendweb, the developer of Smart Slider 3. Nextendweb acknowledged the report on **March 2** and on **March 24** delivered a patch with the release of Smart Slider version **3.5.1.34**.

According to WordPress.org stats, the plugin was downloaded **303,428 times** over the past week. This means that at least **500,000 WordPress sites** are running a vulnerable version of the Smart Slider 3 plugin and are exposed to attacks.

To read the complete article see:
[Read full article](https://www.bleepingcomputer.com/news/security/file-read-flaw-in-smart-slider-plugin-impacts-500k-wordpress-sites/)