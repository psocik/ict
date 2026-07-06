---
title: PamStealer Mimics Maccy Clipboard Manager Silently Harvests Data and Clipboard Contents
date: 2026-07-04
categories: [CYBERSECURITY]
tags: [MALWARE,MACOS,INFOSTEALER,CYBERSECURITY]
---

## PamStealer: A New Threat to macOS Users 🚨

PamStealer is a newly identified macOS infostealer that disguises itself as the popular open-source clipboard manager **Maccy** while silently harvesting sensitive user data. Discovered by **Jamf Threat Labs**, the malware employs a stealthy two-stage infection chain designed to evade detection and blend into normal macOS activity.

### How the Attack Works 🔍
The attack begins with a malicious disk image file named **Maccy.dmg**, which contains a compiled AppleScript file (.scpt). When opened, the file displays harmless-looking instructions prompting the user to press **Run**. This simple social engineering trick triggers the hidden malicious code embedded deep within the script.

In the first stage, the AppleScript acts as a lightweight dropper. Instead of relying on common command-line tools like **curl** or **zsh**, it executes a **JavaScript for Automation (JXA)** payload using native macOS APIs such as **NSURLSession**. This approach reduces visible system activity and avoids raising suspicion. The script downloads a second-stage payload and installs it on the system, often masquerading as a legitimate macOS component, such as **Finder** or **Software Update**.

PamStealer includes environment-aware checks before executing. If the device does not match the expected profile, the malware silently exits. It also avoids systems in specific regions, including **Russia** and neighboring countries, by checking language settings and keyboard layouts.

### The Second Stage: Rust-Based Mach-O Binary ⚙️
The second stage is a Rust-based Mach-O binary, which is relatively uncommon in macOS malware. This infostealer performs a range of malicious activities, including credential theft, clipboard monitoring, and data exfiltration. It accesses browser databases using **SQLite** to extract stored passwords, cookies, and wallet data. It also dynamically loads macOS Security frameworks to access **Keychain** data without exposing its capabilities during static analysis.

One of the most notable features of PamStealer is its password harvesting technique. The malware displays a fake system prompt asking the user to enter their password. It then validates the password locally using macOS **Pluggable Authentication Modules (PAM)**, ensuring only correct credentials are captured. This method avoids suspicious system calls and reduces the number of detection opportunities.

Clipboard data is continuously monitored using the built-in **pbpaste** utility. The malware repeatedly collects clipboard contents at irregular intervals, potentially capturing sensitive information such as passwords, tokens, or cryptocurrency addresses.

### Persistence Mechanisms 🔒
For persistence, PamStealer registers itself as a login item using both modern and legacy macOS APIs. It also drops a helper binary disguised as **System Settings** to reinforce persistence mechanisms. Additionally, it attempts to trick users into granting **Full Disk Access** via fake system alerts, thereby increasing its ability to access sensitive files.

The malware communicates with its command-and-control server at **avenger-[REDACTED BY DNB EDITORS TO GET PAST GOOGLE FILTERS][.]live**, sending encrypted data using **ChaCha20-Poly1305** within JSON requests. Jamf Threat Labs observed connections to public **Ethereum RPC** endpoints, suggesting the malware may use blockchain infrastructure for resilient command-and-control or payload retrieval.

### Conclusion 🛡️
PamStealer highlights the evolving sophistication of macOS threats. By combining native APIs, Rust-based payloads, and advanced social engineering, attackers are creating quieter, more effective malware that is harder to detect with traditional methods.

For more details, check out the full article: [Read full article](https://cybersecuritynews.com/pamstealer-mimic-as-maccy-harvest/)