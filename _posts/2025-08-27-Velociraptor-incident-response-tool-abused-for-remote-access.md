---
title: Velociraptor incident response tool abused for remote access
date: 2025-08-27
categories: [SECURITY]
tags: []
---

In August 2025, Counter Threat Unit™ (CTU) researchers investigated an intrusion that involved deployment of the legitimate open-source Velociraptor digital forensics and incident response (DFIR) tool. In this incident, the threat actor used the tool to download and execute Visual Studio Code with the likely intention of creating a tunnel to an attacker-controlled command and control (C2) server. Enabling the tunnel option in Visual Studio Code triggered a Taegis™ alert, as this option can allow both remote access and remote code execution and has been abused by multiple threat groups in the past.

Organizations should monitor for and investigate unauthorized use of Velociraptor and treat observations of this tradecraft as a precursor to ransomware.

To read the complete article see:
[Velociraptor incident response tool abused for remote access](https://news.sophos.com/en-us/2025/08/26/velociraptor-incident-response-tool-abused-for-remote-access/) 🌐