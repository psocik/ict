---
title: Improper Limitation of a Pathname to a Restricted Directory
date: 2026-10-02
categories: [SECURITY]
tags: [VULNERABILITY,FORTIGUARD,PATH-TRAVERSAL,SECURITY-ALERT]
---

## Improper Limitation of a Pathname to a Restricted Directory

**Source:** Fortiguard  
**Date Published:** October 2, 2026  

An Improper Limitation of a Pathname to a Restricted Directory ('Path Traversal') [CWE-22] and Improper Neutralization of NULL Byte or NULL Character [CWE-158] vulnerability may allow an unauthenticated attacker to write arbitrary files on the underlying system via crafted HTTP or HTTPS requests. This vulnerability has been reported to be exploited in the wild, and customers are urged to apply the workaround below. 🚨

### Workaround
The primary workaround involves disabling the IBE feature support via the GUI (Encryption -> IBE -> IBE Service 'off') or with the following CLI command:  
`config system encryption ibe set status disable end`. Alternatively, organizations can disable access to the FortiMail webmail interface from the internet or limit the access only from trusted private networks. Additionally, if a Web Application Firewall is deployed in front of FortiMail, it can be configured to block POST requests to `/ibe` that contain `'../'`.  

### Indicators of Compromise (IoC)
Indicators of Compromise for this activity include the following IPs: 79.141.[REDACTED] and 45.129.[REDACTED]. System Event Logs may reveal entries such as:  
`type=event subtype=system pri=debug user=system ui=cron msg="(root) CMD (/bin/sh -c 'O=/migadmin ...` and  
`type=kevent subtype=config pri=information user=admin ui=cli module=unknown submodule=unknown msg="Added 'archive234' to 'archive account' : rotation-size[50]rotation-time[1] rotation-hour[14]destination[remote]remote-ip[79.141.[REDACTED]]remote-username[archive234]remote-password[***]remote-directory[/uploads] (user: admin, from: cli)"`.  

### Encryption Logs
Encryption Logs may also show suspicious activity, including entries like:  
`FortiMail::IBE::DecrypterMediaIn::DecrypterMediaIn(FortiMail::MediaIn&, const FortiMail::IBE::KeyFinder&, const FortiMail::EmailAddress&, const FortiMail::Buffer&, FortiMail::IBE::DecrypterMediaIn::Version): Caught BufferException(2), BufferImpl.cpp:973, 'Invalid Base64 Encoding at pos 0. Character=0x2a'` and  
`Internal user *@domain.tld failed to log in.`  

This vulnerability was internally discovered and reported by Gwendal Guégniaud of the Fortinet Product Security team. The initial publication of this alert was on 2026-10-01.  

For more details, please check the complete article: [Read full article](https://www.fortiguard.com/psirt/FG-IR-26-175)  

---