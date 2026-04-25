---
title: Critical Vulnerabilities Found in Tridium Niagara Framework
date: 2025-07-23
categories: [VULNS]
tags: [VULNERABILITIES,TRIDIUM,NIAGARA FRAMEWORK,IOT,SECURITY]
---

**Tridium’s Niagara Framework®** is a leading software framework designed to connect, manage, and control diverse devices in building management, industrial automation, and smart infrastructure environments. It acts as a middleware platform that enables different systems — such as HVAC, lighting, energy management, and security — to interoperate seamlessly, making it a critical backbone for many internet of things (IoT) technologies across industries worldwide.

Recently, researchers at Nozomi Networks uncovered 13 vulnerabilities affecting the Tridium Niagara Framework®. These vulnerabilities are fully exploitable if a Niagara system is misconfigured, thereby disabling encryption on a specific network device (which produces a warning on the security dashboard). If chained together, they could allow an attacker with access to the same network — such as through a Man-in-the-Middle (MiTM) position — to compromise the Niagara system. However, this would depend on a specific network service being configured without encryption, allowing the attacker to collect sensitive data from the network.

In response, Tridium worked swiftly to issue a security advisory and released patches to address these vulnerabilities.  

To read the complete article see:
[Read More](https://www.nozominetworks.com/blog/critical-vulnerabilities-found-in-tridium-niagara-framework) 