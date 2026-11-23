---
title: Mmd 073 2026 Linuxeasyshell New Rust
date: 2026-11-20
categories: [MALWARE]
tags: [MALWARE,RUST,LINUX,SECURITY]
---

## Mmd 073 2026 Linuxeasyshell New Rust

This case started from a shell script spotted in the victim's node. The script is a multi-platform installer (stager), and the binary it delivers is a Rust beacon implant that I could not find in any public threat report at the time of writing. I would like to note that this is one of the earliest publicly documented LoongArch64 RAT implementations, identified within the EasyShell multi-platform Rust implant family. It is an installer, not an uninstaller: Linux and macOS, root or user.

The stager finds a writable system bin directory with the writeablex probe. It picks one of seven payloads by OS and CPU: Linux x86, x86_64, ARM, ARM64, LoongArch; macOS Intel and Apple Silicon. It downloads from C2 IP 192[.]3.31[.]148:8443 with curl, wget or python, TLS checks off, and saves the payload as polkitd (fake system daemon name). For macOS, it hides the file, removes quarantine, ad-hoc signs it (Gatekeeper handling). The payload is a statically linked Rust implant, built after 2026-04-14, with the framework name EasyShell in its own build paths. The C2 is 192[.]3.31[.]148 on tcp/8443, AS36352 ColoCrossing (HostPapa), US. The protocol uses HTTPS POST /api/v2/sync with an X-Client-Id header, Windows Chrome 131 UA, and zh-CN Accept-Language. Encryption and obfuscation involve TLS (rustls) and XOR 0x5A string pool.

RAT remote commands include PTY shell, plugin and script execution, file upload/download, folder zip, SOCKS5 and relay tunnels, outbound proxy, screenshot, process list and kill, self delete. Plugins for credential dumping, token elevation, browser passwords and file search are not built in; they come from the "Extensions" plugin set. Anti-sandbox checks include DMI, hypervisor names, mouse activity, CPU, RAM, uptime checks. Stealth features include a kernel-thread process name table ([kworker/0:0] style), and no shell history. Framework identification confirms it as a client of the EasyShell red team C2 framework; operator unknown. The compromised host where the stager of this case was re-run was a central multi-tenant C2 server housing six co-located Android and iOS malware frameworks (including Fisher C2 and Caishen iOS C2 V2). The attacker used forged JWTs and direct SQLite/MySQL queries to enumerate and hijack active Android and iOS victim botnets. Full source code, APK builders, and iOS exploit chains were archived and exfiltrated before the attacker wiped staging files to free disk space. The attacker deployed ripgrep to systematically carve cryptocurrency seeds, EVM private keys, GitHub tokens, and SSH credentials from raw database tables and victim backups.

[Read full article](https://blog.malwaremustdie.org/2026/11/mmd-073-2026-linuxeasyshell-new-rust.html)\n