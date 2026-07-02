---
title: RustDuck Botnet Rebuilds in Rust to Hijack Routers and Servers for DDoS
date: 2026-07-01
categories: [CYBERSECURITY]
tags: [RUSTDUCK,MALWARE,DDOS,CYBERSECURITY,ROUTERS]
---

## RustDuck Botnet Rebuilds in Rust to Hijack Routers and Servers for DDoS 🚀

A new two-stage malware family called **RustDuck** is hijacking home routers, IP cameras, Android boxes, and poorly secured servers, stitching them into a network built to knock websites and online services offline. Researchers at QiAnXin's XLab have tracked it since February 2026. The end goal is a **distributed denial-of-service (DDoS)** attack: flooding a target with junk traffic from the infected machines until it buckles. 

RustDuck stands out for two reasons: It is being rewritten from the C programming language into Rust, and its newer versions go to unusual lengths to avoid being studied or shut down.

### How RustDuck Spreads
RustDuck spreads by exploiting a mix of old, well-known vulnerabilities. The first method involves devices left on the internet with weak or default passwords on their remote-login services (Telnet and SSH). The second method targets unpatched device bugs; XLab notes RustDuck goes after exposed Android debugging interfaces and flaws in gear from TVT (DVRs and cameras), Ruijie, TP-Link, and ZTE. Additionally, it exploits specific vulnerabilities such as:
- **CVE-2017-17215** in Huawei HG532 routers
- **CVE-2025-29635** in discontinued D-Link DIR-823X routers
- **CVE-2024-1781** in Totolink X6000R routers
- **CVE-2018-8007** in Apache CouchDB

The third path involves web software, with RustDuck also targeting known holes in ThinkPHP, Jenkins, and Hadoop YARN. XLab counted more than 20 internet addresses spreading the malware, with the busiest at 176.

### Installation and Evasion Techniques
RustDuck installs in two stages: a small loader that decrypts and unpacks a heavier core module. This core is being rewritten in Rust. Rust binaries are generally tougher for analysts to dissect than the C that has powered device malware for years. XLab says RustDuck's Rust core shows real depth in how it derives its keys, hides from analysis, and communicates with its servers.

The newer samples work hard to stay hidden. Before doing anything, RustDuck runs a checklist to determine whether it has landed in a security researcher's lab instead of on a real victim's device. It looks for analysis tools like Wireshark and gdb, for debuggers attached to its own process, for the fingerprints of a honeypot trap, and even for virtual-machine hardware. If a threshold is crossed, the malware erases its traces and quits.

Its communications are locked down, encrypting traffic with modern ciphers: **ChaCha20-Poly1305** for the handshake, **AES-GCM** once it is taking commands. It derives its keys with **HKDF-SHA256** and a **Curve25519** exchange, rotates them every ten minutes, and disguises the connection to look like ordinary encrypted web traffic.

### Defense Strategies
There is no patch for RustDuck itself, because it is malware. Defense means closing the doors it walks through. Organizations should:
- Get remote-management interfaces off the public internet.
- Turn off Android Debug Bridge, Telnet, and SSH where they are not needed.
- Never leave them reachable with default passwords.
- Patch what you can and replace what you can't. Unsupported gear has to be replaced, not fixed; for example, CISA's advice for the D-Link DIR-823X is to pull it from service.
- Finally, block the known indicators; XLab's report lists the malware's file hashes, control domains, and source addresses for monitoring.

For more detailed information, you can read the full article here: [Read full article](https://thehackernews.com/2026/06/rustduck-botnet-rebuilds-in-rust-to.html)