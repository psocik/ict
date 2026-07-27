---
title: Bing Images Flaws Let Crafted SVGs Run Commands as SYSTEM on Microsoft's Servers
date: 2026-07-24
categories: [SECURITY]
tags: [BING,SVG,MICROSOFT,SECURITY,VULNERABILITIES]
---

## Bing Images Vulnerabilities 🚨

A crafted SVG submitted to Bing's image search ran commands as **NT AUTHORITY\SYSTEM** on Microsoft's production image-processing workers, and as root on the Linux machines in the same fleet. XBOW's testing confirmed the same result across different hosts and network ranges, indicating a significant issue within Bing's image tier.

Microsoft issued two critical CVEs, **CVE-2026-32194** and **CVE-2026-32191**, both rated **9.8** on the CVSS scale. XBOW, the autonomous offensive security startup, discovered and reported these vulnerabilities privately. Currently, Bing users have no patch or mitigation to apply, as Microsoft resolved both issues server-side before the advisories were released in March, stating there is "no customer action to resolve."

### Exploit Mechanics 🔍

The application mistakenly believed it was handling an image; however, the underlying helper read part of that image as a command. The payload was a one-pixel SVG that executed a command on the worker and returned the output to a collector controlled by XBOW. This vulnerability provided two routes into the same conversion tier, resulting in two CVEs:
- **CVE-2026-32194**: Command injection via the public "Search by Image" upload.
- **CVE-2026-32191**: OS command injection through the crawler route.

### Recommendations 🛡️

An image-processing worker handling untrusted files should not reach a shell, run as SYSTEM, or have internet access. Bing's pipeline unfortunately allowed all three. To mitigate such vulnerabilities, it is crucial to:
- Deny delegates outright in `policy.xml`.
- Cut the formats accepted, avoiding SVG, MVG, and EPS.
- Review `delegates.xml` and disable unnecessary features.
- Run conversion in a sandboxed environment with reduced privileges.
- Block outbound network access from the worker.

XBOW CISO Nico Waisman summarized the situation well: 'Applications treat image helpers as plumbing. Attackers treat them as parsers.'

For more details, [Read full article](https://thehackernews.com/2026/07/bing-images-flaws-let-crafted-svgs-run.html)