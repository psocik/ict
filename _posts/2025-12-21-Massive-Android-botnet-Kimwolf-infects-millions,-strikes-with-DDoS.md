---
title: Massive Android botnet Kimwolf infects millions, strikes with DDoS
date: 2025-12-21
categories: [SECURITY NEWS]
tags: [ANDROID,BOTNET,DDOS,KIMWOLF]
---

Kimwolf is a newly discovered Android botnet linked to the Aisuru botnet that has infected over 1.8 million devices and issued more than 1.7 billion DDoS attack commands, according to XLab.

The Kimwolf Android botnet primarily targets TV boxes, compiled using the NDK and equipped with DDoS, proxy forwarding, reverse shell, and file management functions. It encrypts sensitive data with a simple Stack XOR, uses DNS over TLS to hide communication, and authenticates C2 commands with elliptic curve digital signatures. Recent versions even incorporate EtherHiding to resist takedowns via blockchain domains.

On December 1, researchers took over a Kimwolf C2 domain, revealing over 3.66 million cumulative infected IPs, peaking at ~1.83 million on December 4. Subsequent takedowns on other C2s forced operators to reconfigure, reducing daily active nodes to ~200,000. Observations and comparisons with Aisuru suggest Kimwolf’s DDoS capacity nears 30 Tbps. High-profile attacks on November 23 and December 9 confirmed its involvement. Kimwolf and Aisuru share infection scripts and likely operate under the same group.

To read the complete article see:
[Security Affairs](https://securityaffairs.com/185921/malware/massive-android-botnet-kimwolf-infects-millions-strikes-with-ddos.html)!