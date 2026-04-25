---
title: Scans for EncystPHP Webshell
date: 2026-04-13
categories: [CYBERSECURITY]
tags: [ENCYSTPHP,WEBSHELL,FREEPBX,MALWARE]
---

## Scans for EncystPHP Webshell 🚨

Today, I noticed some scans for what appears to be the **"EncystPHP" web shell**. Some attackers are paying attention and are deploying webshells with more difficult-to-guess credentials. Fortinet wrote about this webshell back in January, and it appears to be a favorite among attackers compromising vulnerable FreePBX systems.

The requests I observed look like:
```
GET /admin/modules/phones/ajax.php?md5=cf710203400b8c466e6dfcafcf36a411
Host: [victim ip address]:8000
User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:89.0) Gecko/20100101 Firefox/89.0
Accept-Encoding: gzip, deflate
Accept: */*
Connection: keep-alive
```
This URL matches what Fortinet reported back in January. The parameter name **"md5"** is a bit misleading. The webshell will just compare the string. The parameter is not necessarily the MD5 hash of a specific **"password"**; any string will work as long as it matches the hard-coded string in the webshell. The string above has the correct length for an MD5 hash, but I wasn't able to find it in common MD5 hash databases. It is very possible that only a few different values are used across different attack campaigns. Many attackers may just **"copy/paste"** the code, including this access secret.

Currently, these probes originate from **160.119.76.250**, an IP address located in the Netherlands. The same IP address is also probing for various FreePBX vulnerabilities, for example:
```
/restapps/applications.php?linestate=$$LINESTATE$$&user=100
```
If you are using FreePBX, you may want to check for these accounts just to make sure.

To read the complete article see: [Read full article](https://isc.sans.edu/forums/diary/Scans%20for%20EncystPHP%20Webshell/32892/)