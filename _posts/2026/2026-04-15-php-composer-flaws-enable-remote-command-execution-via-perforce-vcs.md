---
title: PHP Composer Flaws Enable Remote Command Execution via Perforce VCS
date: 2026-04-15
categories: [SECURITY]
tags: [PHP,COMPOSER,SECURITY,VULNERABILITIES]
---

## PHP Composer Vulnerabilities 🚨

Two high-severity flaws in **PHP Composer** could allow attackers to run arbitrary commands via malicious repository configurations and crafted inputs affecting **Perforce VCS**. PHP Composer is a dependency manager for PHP that helps developers install and manage the libraries their projects need.

### Details of the Vulnerabilities

The flaws impact the Perforce VCS driver and stem from improper input validation and insufficient escaping. By crafting a malicious `composer.json` or source reference with shell metacharacters, an attacker controlling a repository configuration could execute commands on the user's system. 

**Immediate Action Required:** Please update Composer to version **2.9.6** or **2.2.27 (LTS)** by running `composer.phar self-update`. The new releases include fixes for two command injection security vulnerabilities in the Perforce VCS driver.

### Vulnerability Reports
- **CVE-2026-40261** was reported by Koda Reef.
- **CVE-2026-40176** was reported by saku0512.

**CVE-2026-40176** (CVSS score: 7.8) allows an attacker controlling a malicious `composer.json` with a Perforce VCS repository to inject arbitrary commands, leading to execution in the context of the user running Composer. 

**CVE-2026-40261** (CVSS score: 8.8) allows an attacker to inject arbitrary commands via a crafted source reference containing shell metacharacters.

### Mitigation Steps
To mitigate **CVE-2026-40261**, avoid installing dependencies from source by using `-prefer-dist` or setting `preferred-install` to `dist`, and rely only on trusted repositories. For **CVE-2026-40176**, review `composer.json` files carefully, ensuring Perforce fields are valid and running Composer only on trusted projects.

According to the advisory, scans of Packagist.org and Private Packagist found no exploitation attempts. As a precaution, Perforce metadata publishing and the Perforce VCS driver were disabled on **April 10, 2026**.

For more information, [Read full article](https://securityaffairs.com/190824/security/php-composer-flaws-enable-remote-command-execution-via-perforce-vcs.html)