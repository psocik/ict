---
title: This Is Not a Drill' Critical PHP Vulnerabilities Are Setting the Internet on Fire
date: 2026-10-21
categories: [SECURITY]
tags: [PHP,VULNERABILITIES,SECURITY,INTERNET]
---

## 🚨 Critical PHP Vulnerabilities Alert!

On Wednesday, the developers behind the widely-used PHP programming language released emergency security updates to address critical flaws that could allow attackers to gain dangerous remote control of victim systems. The PHP Foundation detailed two critical vulnerabilities—CVE-2026-109618 and CVE-2026-109619—which impact **all PHP installations serving web requests** dating back to PHP version 5, released in July 2004. However, only PHP 8.2 and newer versions are still supported and will receive patches, according to the alert.

This is a significant caveat because foundational web layers like PHP can persist forgotten and un-updated in historic internet infrastructure. 

> "There are no complete mitigations; updating is the only safe choice," the PHP Foundation stated in its advisories. Security experts warn of the potential dire consequences of overlooking unpatched systems. **"This is not a drill,"** says Lukasz Olejnik, an independent security consultant and visiting senior research fellow at King's College London.

Since its inception in the 1990s, PHP has evolved into an essential scripting language for web development, utilized across vast swaths of the internet in various websites and software. Everything from publishing systems like WordPress and Drupal to e-commerce platforms like Adobe's Magento is built on PHP. Olejnik likens the widespread use of the programming language to critical infrastructure, stating, **"The impact is enormous"** regarding PHP's security flaws, adding that millions of systems could be affected. He warns, **"Worst case is wormable malware affecting big chunks of the internet."**

The overriding fear for security teams and developers is that malicious hackers could quickly exploit the vulnerabilities before they are patched. Internet infrastructure company Cloudflare reported it was **"seeing early attacks emerging"** before the PHP Foundation had detailed the vulnerabilities and released fixes. Security firm Sansec anticipated mass attacks to commence within **15 minutes** of the release, which occurred just before **10 am ET** on Wednesday.

Longtime security and compliance consultant Davi Ottenheimer explains, **"Most of the web runs on PHP, and this bug is in a file upload interface that's like a front door with no lock."** Ottenheimer adds, **"An attacker does not need to know which site they are hitting or even the actual software it runs. They send one crafted upload to any server they can find, and that is the entire attack."**

For more details, [Read full article](https://www.wired.com/story/this-is-not-a-drill-2-php-vulnerabilities-are-setting-the-internet-on-fire/).