---
title: Attackers Adopt JavaScript Runtime Bun to Spread NWHStealer
date: 2026-05-06
categories: [MALWARE]
tags: [MALWARE,NWHSTEALER,JAVASCRIPT,BUN,CYBERSECURITY]
---

## Attackers Adopt JavaScript Runtime Bun to Spread NWHStealer 🚨

In our previous research, we analyzed a Windows infostealer we track as **NWHStealer**. The attackers behind this stealer are continuously finding new methods to distribute it. During our hunting activities, we noticed how attackers are using a JavaScript runtime called **Bun** to help distribute it. Bun is a legitimate, fast, all-in-one JavaScript and TypeScript toolkit designed as a modern, high-performance replacement for Node.js. Its relative newness makes it appealing for attackers. Bun has not yet been widely seen in malware campaigns, and it allows them to package malicious code into larger executables that may be less easily detected.

NWHStealer is a Rust-based stealer distributed using a range of lures and delivery methods. These include Node.js scripts, MSI installers, and JavaScript loaders built with the Bun runtime. It is often hosted on legitimate platforms such as GitHub, GitLab, MediaFire, Itch.io, and SourceForge, which helps it blend in with normal software. Once installed, NWHStealer can:
- Collect system information
- Steal data from browsers, extensions, and crypto wallets
- Steal data from applications such as FileZilla, CoreFTP, Steam, and Discord
- Inject malicious code into browser processes and run additional payloads (e.g., XMRig)
- Attempt to bypass User Account Control (UAC)
- Achieve persistence via scheduled tasks
- Get new command-and-control (C2) addresses from Telegram

In recent campaigns, we detected that NWHStealer is being distributed using a Bun JavaScript Runtime bundle. The infection chain starts with an archive containing Installer.exe, which embeds JavaScript code bundled with the Bun runtime. The executed JavaScript code by the Bun JavaScript runtime is inside the .bun section and is obfuscated. The malicious code is implemented in two parts: **sysreq.js** performs anti-virtualization checks with a score system, and **memload.js** communicates with the C2 server, performs decryption, and loads the next stage. The loader runs several PowerShell CIM and WMI commands to detect virtual environments, checking for CPU numbers, disk space, screen resolution, hardware manufacturers, and specific virtual environment indicators. A scoring system determines whether to continue with the infection. The loader obtains and sends an initial request to the C2 server with encrypted data about the compromised system, including public IP, system information, anti-VM result, and a Base-64 encoded screenshot. It then makes two GET HTTP requests to obtain the seed for AES key derivation and the encrypted payload. The next stage is decrypted using AES-256-CBC and loaded with a self-injection loader using Win32 APIs, executed through the Bun module `bun:ffi`. At the end of this process, NWHStealer was deployed.

Attackers are constantly adapting their techniques, and the use of newer tools like Bun shows how they try to stay ahead of detection. NWHStealer is particularly concerning because of how widely it is distributed and the types of data it targets. Stolen browser data, saved passwords, and cryptocurrency wallet information can quickly lead to account takeovers, financial loss, and further compromise. 

### Mitigation Advice:
- Only download software from official websites.
- Be cautious with downloads from platforms like GitHub, SourceForge, or file-sharing platforms unless you trust the source.
- Check the file's publisher and signature before you run it.

Key Indicators of Compromise (IOCs) include C2 domains such as `whale-ether[.]pro`, `cosmic-nebula[.]cc`, and `silent-harvester[.]cc`. An example hash associated with this activity is `d3a896f450561b2546b418b469a8e10949c7320212eb1c72b48e2b1e37c34ba5`.

[Read full article](https://www.malwarebytes.com/blog/threat-intel/2026/05/attackers-adopt-javascript-runtime-bun-to-spread-nwhstealer)