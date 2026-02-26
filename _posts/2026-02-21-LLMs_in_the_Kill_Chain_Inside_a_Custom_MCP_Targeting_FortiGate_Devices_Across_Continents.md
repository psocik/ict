---
title: LLMs in the Kill Chain - Inside a Custom MCP Targeting FortiGate Devices Across Continents
date: 2026-02-21
categories: [CYBERSECURITY]
tags: [LLMS,KILL-CHAIN,FORTIGATE,CYBERSECURITY,INTRUSION]
---

## LLMs in the Kill Chain - Inside a Custom MCP Targeting FortiGate Devices Across Continents

In early February 2026, a misconfigured server with more than one thousand files was found exposed to the internet. Among them were stolen firewall configurations, Active Directory maps, credential dump output, and detailed attack plans targeting organizations across multiple continents. What made this particular server different was a software pipeline integrating large language models (LLMs) directly into the intrusion workflow. A historical review revealed a previous exposure in December 2025 containing similar tooling alongside additional victim data.

The models used in this case were not involved in writing exploits or discovering zero-days. Instead, they were used for triaging compromised targets and generating attack plans quickly enough to keep multiple intrusions moving concurrently. An open directory exposed the full toolkit of an active intrusion campaign with confirmed victims in at least five countries.

### The Malicious Operation

The malicious operation automates backdoor creation on compromised Fortinet appliances, connects to victim networks, maps internal infrastructure, and feeds results to language models for analysis. DeepSeek is utilized to generate attack plans from reconnaissance data. Claude’s coding agent produced vulnerability assessments during the intrusions and was configured to execute offensive tools on the victim systems. A previously unreported model context protocol (MCP) server acts as a bridge to the language models, maintaining a knowledge base that grows with each target.

Between the two time frames observed, the actor evolved from using an open-source offensive MCP tool to a fully automated exploitation system. The server at 212.11.64[.]250:9999 contained 1,402 files across 139 subdirectories, including CVE exploit code, FortiGate configuration files, Nuclei scanning templates, and Veeam credential extraction tools.

### Previous Instances

The earlier instance contained a copy of HexStrike, an open-source offensive security framework that enables large language models to run penetration testing tools using the MCP. The server also hosted BloodHound collection data, output from exploit code, attack reports, and a .claude directory with a settings.json file in it. This file pre-approved Claude Code to autonomously run Impacket, Metasploit, hashcat, and other offensive tools using hardcoded domain credentials belonging to an employee of a large media company based in Asia.

The same IP appeared in operational logs as the source address for SSH sessions used to modify FortiGate appliance configurations across multiple countries. This confirms the server was actively participating in the intrusion. Confirmed compromises affected an industrial gas company in the Asia-Pacific region, a telecom provider in Turkey, and the media company identified in December. Additional reconnaissance referenced targets in South Korea, Egypt, Vietnam, and Kenya, along with code targeting a medical equipment manufacturer.

### Targeted Data

The most complete intrusion data observed targeted the gas company. The starting point was a FortiGate-40F appliance at a branch office, accessed through a read-only admin account, which extracted the full backup configuration exposing network topology for the headquarters network, a branch office subnet, guest and management networks, and SSL VPN settings including all configured user accounts. A markdown file cataloged 50 VPN user accounts by name and employee ID, LDAP server settings, and the organization’s domain controller (DC) details.

Two Python scripts on the server linked to CVE-2019-6693 likely decrypted passwords from the backup file. With valid credentials and a full network map, the threat actor shifted to an automated strategy. Scan results and recon data were processed through a custom MCP server. A Claude Task file provided insight into the operator’s thinking while relaying input to the model, concluding with four specific requests: attack vectors for targets out of reach, credential search locations on DC shares, methods to identify IT staff, and a prioritized path to Domain Admin.

An assessment report, attributed to Claude Code and dated February 1, 2026, documented two primary internal targets: a QNAP NAS and a Veeam Backup server. Multiple exploitation attempts were recorded using a mix of Metasploit modules and publicly available exploit code. Output data also showed a running ntlmrelayx.py process, part of the Impacket suite, actively capturing credentials and authenticating against specific targets.

[Read full article](https://cyberandramen.net/2026/02/21/llms-in-the-kill-chain-inside-a-custom-mcp-targeting-fortigate-devices-across-continents/)