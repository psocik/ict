---
title: ENDLESSDOORS Is Phoning Home. Pick Up.
date: 2026-08-05
categories: [CYBERSECURITY]
tags: [ENDLESSDOORS,MALWARE,ZBTLINK,SECURITY]
---

## ENDLESSDOORS Is Phoning Home. Pick Up! 🚨

Zbtlink routers are phoning home, waiting for orders. Not because they were hacked, but because they were shipped that way. These routers are made by Zbtlink, a brand of Shenzhen Zhibotong Electronics, a Chinese manufacturer that builds routers and white-labels them for sale globally. The implant, named **ENDLESSDOORS** by the research team, manifests as two unbracketed kworkers in a process listing, running as root.

The implant is a small tool called **rctl** (remote control linux), uploaded to GitHub on January 14, 2015, implementing a simple command and control client and server. The server listens on port 7000 for clients to connect, sending individual shell commands or spawning a reverse bash shell.

The kworker on an affected AX3000 model is a customized rctl, configured to phone home to **47.107.224[REDACTED]** and **rbdg4nzqadui[REDACTED].com**. The attack mechanism requires no handshake, key exchange, or negotiation, and no client or server verification. After connection, anything the server sends is executed as uid 0 with no allow-list or sandbox. A reserved string, **rctlbash**, tells the implant to open a second connection to port 7001, allocate a pseudo-terminal, spawn **/bin/sh**, and bridge it, resulting in a live interactive root shell. Crucially, anyone along the network path can hijack the client/server communication by controlling the resolution of **rbdg4nzqadui[REDACTED].com**, or its resolved address. Because the device dials out, none of this requires the router to be reachable from the internet. This capability has been assigned **CVE-2026-66747**.

Every firmware on zbtlink.com's download page, roughly two dozen images, embeds the rctl implant and starts it at boot. All of them phone home and are hijackable. Affected models include: CPE2801, WE1026-5G-WD, WE1326, WE2007, WE2008-DSIM, WE2416, WE3326, WE5927, WE5931, WE5931AC, WE826-T3-DSIM, WG108, WG1602, WG1608-DSIM, WG209, WG2105, WG2107, WG259, WG3526, Z8102AX-2DSIM. Affected routers dial endpoints like **rbdg4nzqadui[.]wikaba[.]com** and **zbtctl.epplink[.]net**, which resolves to **47.100.190[.]96**. The researchers did not notify Zbtlink, stating that coordinated disclosure assumes the vendor did not intend the behavior, which does not hold true here. Therefore, they are publishing detection content so defenders can act today.

There is no fixed firmware; this is a device-trust problem. Defenders should inventory by model number, not brand, checking for the listed models under Zbtlink, ZBT, ZBTWiFi, Wiflyer, and unbranded cellular CPE. Detection involves checking the process list for an unbracketed kworker with a nonzero VSZ, or the filesystem for **/usr/sbin/kworker**, **/usr/lib/librctl.so**, **/etc/kworker.cfg**, and **/etc/init.d/skworker**. Block and alert on endpoints **[REDACTED]** at egress and resolver levels, and watch for outbound **7000/7001**. The advice is to replace the device, or move it behind strict egress control and treat its LAN as untrusted.

[Read full article](https://www.vulncheck.com/blog/zbt-endlessdoors)