---
title: LG Smart TV Vulnerabilities Allow Root Access Over Local Network
date: 2026-10-14
categories: [TECHNOLOGY]
tags: [LG,SMART-TV,VULNERABILITIES,SECURITY]
---

## LG Smart TV Vulnerabilities Allow Root Access Over Local Network 🚨

Three vulnerabilities in LG's webOS have been discovered that can be chained together to grant an attacker on the same local network root access to certain smart TVs. This attack can be performed without requiring any user interaction or a PIN. LG has since released a fix for these vulnerabilities, as first reported by The Hacker News.

The vulnerabilities specifically affect LG TV models running webOS 7.5.7-25 on firmware 04.54.40, though it is currently unknown if other versions are impacted. The attack chain begins by exploiting a service on port 3001, which is used by the LG ThinQ app for device pairing. An attacker can replay a manifest from a built-in app, signed with a test certificate that the firmware trusts. This action bypasses the PIN prompt and ultimately grants a privileged key.

With this privileged key, the attacker can then launch another application, cmp-client, and direct it to a malicious page. This malicious page can subsequently access PalmServiceBridge, which is an internal interface to the TV's system services. Through this bridge, the attacker is able to execute commands as root by exploiting the system logging service, pmlogd, which does not properly validate input. Notably, no CVE identifiers have been assigned for these vulnerabilities, and no exploitation in the wild has been reported thus far.

[Read full article](https://www.scmagazine.com/brief/lg-smart-tv-vulnerabilities-allow-root-access-over-local-network)