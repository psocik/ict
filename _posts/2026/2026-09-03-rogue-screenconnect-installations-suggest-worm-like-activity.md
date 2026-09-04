---
title: Rogue ScreenConnect Installations Suggest Worm-Like Activity
date: 2026-09-03
categories: [CYBERSECURITY]
tags: [MALWARE,SCREENCONNECT,CYBERSECURITY,THREAT,VBSCRIPTS]
---

## Rogue ScreenConnect Installations Suggest Worm-Like Activity 🚨

Recently, Huntress observed a strange pattern across unrelated endpoints within several different organizations that we protect. In late August, our Security Operations Center (SOC) sent out three critical incident reports for what looked like malicious ScreenConnect installations and unexpected process executions. All the incidents started with some level of social engineering, which ultimately led to rogue ScreenConnect instances being deployed on the victims' machines. After these rogue ScreenConnect instances were deployed, Huntress observed unexpected process executions: `wscript.exe` was used to deploy four different VBScript files (`1.vbs`, `2.vbs`, `3.vbs`, and `4.vbs`).

The most interesting part of the attack chain was that it used modified ScreenConnect clients to propagate the VBScript chain, specifically executing the four files (`1.vbs` to `4.vbs`) to connected ScreenConnect endpoints, creating a worm-like spread across newly connected systems. Huntress observed several other similarities across the incidents, including the attacker creating a User Run Key (`WindowsServiceHost`) that pointed to a VBScript file (`WindowsServiceHost.vbs`) in impacted users' `AppData` directories. In one August 20 incident, the threat actor deployed a rogue ScreenConnect remote access client, configured to communicate with a command-and-control (C2) server.

An analysis of the payloads used in the attack revealed a staged attack designed to profile hosts and conceal activity. The first suspect script, `1.vbs`, creates a three-bit "state" variable by profiling various aspects of the system on which it is running. This includes enumerating security products, including Huntress, Cisco AMP, CrowdStrike, SentinelOne, Sophos, and Malwarebytes. If Microsoft Defender appears to be the sole endpoint protection utility, it sets the second bit value to 1. `2.vbs` waits for the presence of this `value.txt` file, and if it does not contain the word `abort`, it downloads a file from Dropbox. It then decodes the file's content from base64 encoding and performs an XOR on the data, which it writes out to `%TEMP%\map.txt`. That decoded content is placed into `%TEMP%\map.txt`, but not executed - it is used as a catalogue of further staged payloads for the rest of the attack chain.

In an update on September 3, ConnectWise published an advisory. They stated they have identified an issue impacting "file transfer behavior" in ScreenConnect Remote Access Support and Access sessions (both cloud and on-premise deployments). ConnectWise said that a CVE and official fix will be issued within the week. ConnectWise suggested that potentially impacted organizations check the TransferFiles permissions, or TransferFilesInSession in legacy versions, and disable this option if it is enabled.

[Read full article](https://www.huntress.com/blog/rogue-screenconnect-installations)