---
title: Alpine Linux and OpenSSH Patch Flaw Exposed
date: 2026-11-06
categories: [SECURITY]
tags: [ALPINE,LINUX,OPENSSH,VULNERABILITY,SECURITY]
---

## Alpine Linux and OpenSSH Patch Flaw Exposed 🚨

The perfect nightmare scenario for a Linux server is when all an attacker needs to do is reach the server's Secure Shell (SSH) port, waltz right in, and take it over. That's what happened to Alpine Linux, the popular, lightweight Linux server. Most authentication bypasses come from complex logic chains, but yesterday's Alpine Linux OpenSSH vulnerability (CVE-2026-123158) comes down to a single character: *.

If you run Alpine Linux (or another musl-based distro) with the default openssh-server package (no Pluggable Authentication Modules (PAM)) and PasswordAuthentication enabled, an attacker can log into password-disabled or key-only accounts simply by sending a password between 257 and 1024 bytes long. According to *sshole, the group that uncovered the problem, this is a side effect that has been hiding since 2016.

### How It Works 🔍
Behind the scenes, when OpenSSH is built without PAM, it verifies passwords by hashing the password attempt using the C library's crypt() function. But when a key is longer than 256 bytes, musl's crypt() function returns the string * as an error indicator. That is also what the password field holds for any account with no password, such as a key-only account. Thus, the "hash" matches and the login succeeds, allowing the attacker to gain access.

To exploit it, an attacker only needs the name of such an account and at least one other account on the machine with a 5 or 6 password hash, and then to send a password of 257 to 1,024 bytes. According to Alpine, one user with a password is enough to make every passwordless account accessible.

### Affected Systems ⚠️
Alpine Linux isn't the only operating system that uses musl; other potentially vulnerable systems include Adélie Linux, Void Linux, Sabotage Linux, OpenWrt, an Android variant, and the Yocto Project. Alpine said every release it checked is affected: 3.21 through 3.24, edge, and the older 3.16 to 3.20 branches. Alpine singled out its official tiny-cloud images, versions 3.18.11 through 3.24.3, as especially vulnerable, as they ship with an alpine user with a * password field and passwordless doas, becoming exploitable once any 6 hash exists on the machine.

### Mitigation Steps 🔧
Alpine released 3.21.10, 3.22.8, 3.23.8, and 3.24.4 on Thursday, with the OpenSSH fix among the security changes, and published fixed packages for each release back to 3.16. The just-released OpenSSH 10.6p2 also avoids the problem. You should run `apk upgrade -U -a` and then restart the daemon with `rc-service sshd restart`. Alpine stressed that upgrading the package does not replace the running daemon.

Anyone who cannot update should set `PasswordAuthentication no` and restart sshd, after confirming that key login works. Systems are not affected if they are containers that do not run sshd, have password authentication disabled, use openssh-server-pam with UsePAM yes, or have locked accounts with '!' in the password field.

### Monitoring for Attacks 🔍
To check for an attack, Alpine advised administrators to search `/var/log/messages` for "Accepted password for" lines that name an account with no password, and review dedicated `doas` use and recently created users, files, and authorized keys. "If you cannot rule out a login, treat the machine as compromised."

For more details, you can read the full article [here](https://www.zdnet.com/tech/alpine-linux-openssh-patch-flaw/).