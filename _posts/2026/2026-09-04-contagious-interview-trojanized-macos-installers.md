---
title: Contagious Interview Trojanized macOS Installers
date: 2026-09-04
categories: [CYBERSECURITY]
tags: [MALWARE,MACOS,SECURITY,TROJAN]
---

## Contagious Interview: Trojanized macOS Installers

Jamf Threat Labs has uncovered fake macOS installers tied to the same infrastructure behind past Git hook and VS Code task file attacks. 🚨 Jamf Threat Labs identified a cluster of macOS disk images (DMG) and installer packages (PKG) impersonating known Mac applications. Every sample in the cluster reaches out to the same staging infrastructure, matching a chain documented by CITIZENDOT in a July 2026 writeup of a fake take-home assignment, and the broader Contagious Interview activity that Jamf Threat Labs and OpenSourceMalware have been tracking through 2026. 

Contagious Interview is a long-running campaign attributed to the DPRK in which attackers use a fake job interview as a pretext to convince victims to run malicious code. The samples described package these same techniques into a series of trojanized installers. 

The cluster was discovered in VirusTotal, starting with `Magic Disk Cleaner.app/Contents/MacOS/.macos`, which led to two shell scripts, `/task/mac` and `/task/tokenlinux`. In total, 14 trojanized samples have been surfaced, spanning both DMGs and PKGs, impersonating applications such as The Unarchiver, Presentify, and PDFify. Initial investigation shows that each modified application is left completely unsigned. The `CFBundleExecutable` within the `Info.plist` has been modified to `.macos`, ensuring the hidden payload is executed when a user double-clicks the application bundle. Due to the lack of a valid code signature and notarization, the trojanized application will be blocked by Gatekeeper. In order to launch the application, the `com.apple.quarantine` must be removed. Once executed, the application removes `com.apple.quarantine` from the standard binary, launches the app as a decoy, and curls down `/task/mac` from C2 at 162.0.239[REDACTED BY DNB EDITORS TO GET PAST GOOGLE FILTERS]. Further analysis revealed that the `.macos` binary is a shell script that has been converted to Go code and then compiled as a standalone Go executable via the open-source project, Bunster. 

The server at 162.0.239[REDACTED BY DNB EDITORS TO GET PAST GOOGLE FILTERS] returns a short bash script whose only job is to fetch and run the next stage, `/task/mac`. This staging has moved from `~/Documents` to the hidden `~/.task` directory. The next script, `tokenlinux.sh`, downloads the official Node.js build from nodejs.org, fetches a malicious `parser.js` and `package.json` from the staging server, runs `npm install`, and then executes the `parser.js` script. This variant requests only the Intel build, once again making Rosetta 2 a requirement. `parser.js` is the final payload in the chain, identified as OtterCookie, a malware family tied to this same Contagious Interview activity. Deobfuscating the payload confirms four components: a Socket.IO-based remote access trojan (scdata), a browser/crypto wallet credential stealer (ldata), an in-memory filesystem scanner, and an in-memory clipboard clipper. The malware is hosted on 162.0.239[REDACTED BY DNB EDITORS TO GET PAST GOOGLE FILTERS], with the listener on port 3000. 

This campaign shows signs that attackers may be testing different delivery mechanisms, as seen in the disk images and packages disguised as legitimate software. The samples do not execute by default, suggesting either active testing or early development. Contagious Interview continues to be a threat to Mac users as operators keep developing alternative methods for delivery.

[Read full article](https://www.jamf.com/blog/contagious-interview-trojanized-macos-installers/) 