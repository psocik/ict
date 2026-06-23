---
title: Thousands of D-Link Routers Under Control of AryStinger Botnet
date: 2026-06-22
categories: [CYBERSECURITY]
tags: [DLINK,BOTNET,MALWARE,CYBERSECURITY]
---

## Thousands of D-Link Routers Under Control of AryStinger Botnet

Researchers have found that the recently discovered **AryStinger botnet** has quietly hijacked thousands of end-of-life D-Link routers and some network-attached storage (NAS) devices, turning them into a distributed scanning and proxy network that attackers can use to hide their activity and launch attacks against other targets. 🚨

The AryStinger botnet is mainly built on compromised D-Link DIR-850L and DIR-818LW routers. Although these devices are long past end-of-life, they are still widely used in homes and small offices, making them attractive targets for botnet operators. The attackers exploited vulnerabilities disclosed 13 years ago to compromise a large number of routers. According to the researchers: "At least 4,300 routers worldwide have already been infected, and the number is still continuously rising." 🌍

By targeting routers that are no longer supported by the vendor, the attackers gain access to devices that will never receive security patches but remain connected to the internet.

AryStinger turns each infected device into what the researchers call an "Executor": a remotely controlled node that can scan networks, act as a proxy, create tunnels, and run commands on behalf of the attacker. The botnet's controller splits large reconnaissance tasks into many smaller ones and distributes them across these Executors, effectively turning a fleet of consumer routers into a large-scale scanning platform. The botnet's primary purpose is reconnaissance at scale. The controller can push scanning jobs (for IP ranges, open ports, DNS records) down to many Executors in parallel and use those results to map networks, identify new vulnerable services, and prepare further compromises ("footprinting").

For owners of infected devices, a more worrying capability is AryStinger's ability to tamper with DNS settings. This allows attackers to redirect victims' browser traffic to phishing pages or malware-hosting sites, and silently monitor and potentially steal all inbound and outbound network traffic passing through the router or NAS. This can put otherwise well-protected devices at risk, as mobile phones, tablets, and laptops connected to the compromised router can be redirected as well. Possible indicators might be slightly slower connectivity, occasional unexplained DNS failures or redirects, or spikes in outbound traffic at odd times. The underlying risks are serious: **Privacy**, as attackers may be able to inspect or redirect traffic, potentially capturing sensitive data; **Liability and reputation**, as your IP address could be used for criminal activity; and **Pivoting into your network**, particularly on compromised NAS devices, to look for additional systems to target.

The most effective solution to this threat is to replace end-of-life routers and NAS devices. If that's not an immediate option, some steps can be taken to make a device harder to compromise. These include applying the latest firmware available for your device, even if it's old, and reviewing any vendor security advisories for known vulnerabilities. Additionally, change the default administrator password to a unique, strong password or passphrase; disable remote management from the internet (WAN); use WPA2 or WPA3 wireless encryption with a strong Wi-Fi password; and turn off unused services such as UPnP on the WAN side or legacy remote access protocols. It is also recommended to run an anti-malware scan on computers and other devices connected to the router. Even if all these recommendations are applied, an end-of-life router should be considered untrusted, and plans to replace it as soon as possible should be made. 🔒

[Read full article](https://www.malwarebytes.com/blog/news/2026/06/thousands-of-d-link-routers-under-control-of-arystinger-botnet)