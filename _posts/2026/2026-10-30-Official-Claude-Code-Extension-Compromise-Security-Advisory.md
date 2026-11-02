---
title: Official Claude Code Extension Compromise Security Advisory
date: 2026-10-30
categories: [SECURITY]
tags: [MALWARE,SECURITY,ADVISORY,CLAUDE,EXTENSION]
---

## Official Claude Code Extension Compromise - Security Advisory 🚨

Phorion has detected a **backdoor** in the official Claude Code for VS Code extension bundle on the Cursor Marketplace. This backdoor drops a persistent SSH backdoor across macOS, Linux, and Windows. Organizations should immediately review their environments for the use of Claude Code for VSCode version 2.1.313 and engage incident response where the extension is discovered.

Cursor has removed the associated release from its marketplace, additionally pulling NPM and VSCode versions for 2.1.313 from their relevant registries. Because extensions run with the permissions of the IDE and the user running it, a backdoored extension gains immediate access to local files, source code, and developer tooling as soon as its module is loaded.

### Technical Details 🔍
The compromised `extension.js` file starts with an injected immediately invoked function expression (IIFE) prepended to the minified extension bundle. The injected prefix pulls in standard Node.js modules and executes as soon as Node loads the file, before the extension's normal activate callback even runs. 

1. The payload ensures that `~/.ssh` exists and appends an attacker-controlled Ed25519 public key to `~/.ssh/authorized_keys`, setting permissions to `0700` on the directory and `0600` on the file. The key uses the comment `svc-telemetry`.
2. With the key in place, anyone holding the matching private key can authenticate as that user, provided SSH is running.
3. The script attempts to enable and start `sshd` or `ssh` via `systemctl` on Linux, checks Remote Login on macOS, and tries to install and start OpenSSH Server using PowerShell on Windows.

### Oversight in Malware Logic ⚠️
Phorion has discovered a likely oversight in how the malware tries to turn on SSH on macOS. The setup logic assumes it can check the current Remote Login state without root privileges. When run as a standard user, `systemsetup -getremotelogin` prints an administrator-access error and exits with status 0. This mistake breaks the inbound access path on a Mac that doesn't already have SSH running.

### Outbound Connection Setup 🌐
The script sets up an outbound SSH connection to `134.209.82[REDACTED BY DNB EDITORS TO GET PAST GOOGLE FILTERS]` as the `tunnel` user on port 22. It decodes a separate embedded private key: an unencrypted OpenSSH Ed25519 key with the comment `svc-telemetry-tun`, used for authentication.

### Persistence Mechanism 🔄
To survive a reboot, the script sets up platform-specific persistence. On macOS and Linux, the `~/.config/.smt` script has the tunnel private key embedded inside it and writes it out to `~/.config/.smtk` before starting the reconnection loop. On macOS, the LaunchAgent disguises itself as `com.apple.sysmond.plist` inside `~/Library/LaunchAgents/`.

For further details, please refer to the complete article: [Read full article](https://phorion.io/blog/offical-claude-code-vsx-compromise/) 

---