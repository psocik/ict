---
title: Suspected Chinese Operators Use Claude Code and DeepSeek to Breach Government Systems Across Four Countries
date: 2026-07-15
categories: [CYBERSECURITY]
tags: [CHINESE,CYBERSECURITY,INTRUSION,GOVERNMENT]
---

## Overview

In June 2026, a pivot from known TencShell C2 infrastructure led us to an open directory exposing an active intrusion campaign. TencShell is a Go-based implant derived from the open-source Rshell framework, first documented by Cato CTRL in May 2026 and assessed there as suspected China-linked. The directory held victim source code, custom exploit scripts, operational logs, and cloned login pages, with the attack notes written in Simplified Chinese. 

What caught our attention was the tooling behind it. **Claude Code** and **DeepSeek-v4-pro** ran as working parts of the intrusion, not tools off to the side. They handled reasoning for bypass techniques, reworked exploits after failed attempts, and built the phishing pages used to harvest credentials. That puts this campaign alongside Anthropic's November 2025 disclosure of a China-linked operation that used Claude Code to automate large-scale intrusions. 🚀

## Key Findings

The open directory on 112.[REDACTED BY DNB ADMINS TO GET PAST GOOGLE FILTERS] exposed a full operational toolkit, including payloads, operator files and scripts, and victim-specific folders. Infrastructure pivots identified 13 Hong Kong-based servers spanning four separate ASNs, three with shared SSH keys and TLS certificates, serving in a redundancy capacity. Active exploitation of government systems in **Afghanistan**, **Thailand**, and **Taiwan** occurred, with reconnaissance and phishing staging against U.S. government portals. Additionally, scanning of 5,890+ government hosts across 10 countries was observed with a Python-developed automated scoring scale. Claude Code handled execution and session persistence while DeepSeek-v4-pro drove the reasoning, a two-model split documented across the recovered log files. 

## Infrastructure Details

Building on public threat research documenting TencShell C2 infrastructure, we pivoted on an HTTP header hash observed on port 1111 of the command and control nodes. This query returned 13 unique IP addresses; the remaining 11 servers, previously unreported, are all located in Hong Kong and distributed across four autonomous systems: VMISS Inc., MEGA-II IDC, CTG Server Limited, and Antbox Networks Limited. Beyond port 1111, the cluster also exposed services on ports 1212 and 8090. 

Among these IPs, 112.[REDACTED BY DNB ADMINS TO GET PAST GOOGLE FILTERS] (MEGA-II IDC, AS152194) was observed hosting an open directory on port 8888. This server was also flagged as high risk for exposing Asset Reconnaissance Lighthouse (ARL) and a Vshell C2 service. The ports and services on this IP supported a complete attack workflow: ARL performed network reconnaissance, DeepAudit, which was found running on port 3000, audits code for vulnerabilities, and Vshell provides command and control. 

For more detailed insights, check out the full article here: [Read full article](https://hunt.io/blog/chinese-operators-claude-deepseek-government-intrusion)