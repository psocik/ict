---
title: Debian and Ubuntu APT Flaw Lets MitM Attackers Swap Verified Packages and Run Code as Root
date: 2026-11-04
categories: [SECURITY]
tags: [DEBIAN,UBUNTU,APT,SECURITY,VULNERABILITY]
---

## Critical APT Flaw in Debian and Ubuntu 🚨

A critical flaw, **CVE-2026-109518**, in APT, the package manager for Debian and Ubuntu, allows an attacker who can modify package downloads to swap a checked package for their own. The attacker's code then runs as root, according to advisories that Debian, Ubuntu, and APT's developers published on **November 4**. APT's developers call the flaw critical. Ubuntu rates the flaw as high priority, with a **CVSS 4.0 score of 7.7**, and says that distributions built on Debian and Ubuntu are affected as well, without naming any.

### Attack Mechanism 🔍
The attack needs APT to retry failed downloads, which it does by default from Debian 12 and Ubuntu 22.04 onward. Older releases, such as Debian 11 and Ubuntu 20.04, are not exposed by default, according to Ubuntu. However, many user scripts may have turned on the retry setting, **Acquire::Retries**, on those releases anyway, APT's developers say. The attacker can be anyone who can change the HTTP traffic between APT and the package server, including a malicious mirror or proxy, according to Ubuntu. The attack runs when the computer installs a package. The attacker uses HTTP redirects and ordinary temporary server errors to make APT retry the download, APT's developers say. Max Justicz reported the flaw.

### Fixes Released 🛠️
Debian has released fixed versions of APT for the flaw. For Debian 11, APT's developers have published a fixed version, **2.2.5**. Debian's testing branch was still on the vulnerable version **3.3.5** at **14:58 UTC** on November 4. Updates for Ubuntu and its Ubuntu Pro subscription service are being released, with Ubuntu 14.04 users with Ubuntu Pro already able to get one. Additionally, Ubuntu published new APT builds for four of its releases to its security archive at **14:25 UTC** on November 4: 
- Ubuntu 26.10 (3.3.3ubuntu0.1)
- Ubuntu 26.04 LTS (3.2.1ubuntu0.1)
- Ubuntu 24.04 LTS (2.8.4ubuntu0.1)
- Ubuntu 22.04 LTS (2.4.15ubuntu0.1)

At **15:46 UTC**, Ubuntu still marked all eight releases it tracks for the flaw, from 14.04 LTS to 26.10, as vulnerable. None of the three advisory reports describe attacks exploiting the flaw or offer a workaround for systems that cannot update yet. They describe the attack over HTTP and do not say whether package sources reached over HTTPS are exposed.

For more details, check the full article here: [Read full article](https://thehackernews.com/2026/11/debian-and-ubuntu-apt-flaw-lets-mitm.html)