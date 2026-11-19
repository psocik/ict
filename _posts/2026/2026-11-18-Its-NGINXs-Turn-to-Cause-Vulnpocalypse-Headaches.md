---
title: It's NGINX's Turn to Cause Vulnpocalypse Headaches
date: 2026-11-18
categories: [CYBERSECURITY]
tags: [NGINX,VULNERABILITIES,CYBERSECURITY,EXPLOITS]
---

## It's NGINX's Turn to Cause Vulnpocalypse Headaches 🚨

Security researchers disclosed five vulnerabilities on November 18, 2026, in NGINX, the web server software that handles traffic for roughly a third of all websites. Each vulnerability comes with a working exploit, with the most severe allowing an unauthenticated attacker to run code on the server from anywhere on the internet. In tests, researchers chained this vulnerability with a separate Linux kernel flaw to take over the machine hosting the server entirely.

F5, the company behind NGINX, released fixes on the same day and published an advisory classifying the worst of the flaws, an integer underflow tracked as CVE-2026-123007, as critical, scoring **9.2 out of 10** on the CVSS scale.

### The Core Problem
The core issue lies in HTTP/2, the protocol NGINX uses to carry many requests over a single connection. HTTP/2 utilizes a credit system; when a client cancels a request while its response data is still waiting to be sent, NGINX hands back that unused credit without checking whether the total now exceeds the protocol's maximum. A later check subtracts the inflated number from the maximum using unsigned arithmetic, which cannot go negative, causing the calculation to wrap into an enormous value. This broken number is treated as a negative response length, leading to a memory buffer whose end pointer sits before its start, resulting in a memory copy that spills outside its boundaries.

### Practical Limits of the Attack
The attack has practical limits: it requires roughly **128 gigabytes** of HTTP/2 traffic, mostly control frames carrying no actual data. The demonstration took two-and-a-half minutes on a fast local network, but would need about two minutes over a **10-gigabit link** and **17 minutes** over **1 gigabit**. Additionally, because NGINX closes connections after an hour by default, a network slower than about **300 megabits per second** cannot finish the attack in time. The exploit also relies on a specific optimized memory-copy routine in the GNU C Library, selected on x86-64 chips with certain AVX-512 features.

### Other Identified Flaws
Other identified flaws affect different NGINX features, including reverse proxying over HTTP/2 and HTTP/3, combinations of the resolver and mirror directives, and mail proxying. Wiz Research, working with Ikotas Labs, Metnir, and Rapid7, independently found two of the same flaws and documented one of them, a use-after-free bug, in reverse-proxy setups where connection slots run low.

Xint, which discovered four of the five flaws with an automated testing harness and no human guidance, went the furthest. The team chained the HTTP/2 bug with a separate flaw in the Linux kernel's SCTP networking code to reach root, the highest privilege level on the host. Brian Pak, co-founder and CEO of Xint, stated, "Others have targeted NGINX with AI pentesting, but none found this critical bug."

F5 mentioned that its cloud services are still being evaluated while BIG-IP and F5OS products were found not vulnerable. Xint's Shodan snapshot found **98.9%** of **11.94 million** version-identifiable NGINX hosts running affected releases, though that counts versions, not confirmed exposure, since it does not show whether each server accepts HTTP/2 or has received a backported fix.

For more details, [Read full article](https://cyberscoop.com/nginx-critical-vulnerabilities-exploits/).