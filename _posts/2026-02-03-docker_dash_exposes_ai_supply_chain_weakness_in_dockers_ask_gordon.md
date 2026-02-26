---
title: DockerDash Exposes AI Supply Chain Weakness In Docker's Ask Gordon
date: 2026-02-03
categories: [CYBERSECURITY]
tags: [DOCKER,AI,SECURITY,SUPPLY_CHAIN]
---

## DockerDash Exposes AI Supply Chain Weakness 🚨

A critical security flaw affecting Docker's Ask Gordon AI assistant has been disclosed by cybersecurity researchers, revealing how unverified metadata can be turned into executable instructions. The issue, dubbed **DockerDash** by Noma Labs, exposes weaknesses across the full AI execution chain, from model interpretation to tool execution, and highlights emerging risks as AI agents are embedded deeper into development workflows.

### Key Findings 🔍

- A single malicious metadata label inside a Docker image can compromise a Docker environment through a three-stage process.
- Ask Gordon reads the metadata, forwards the interpreted instruction to the Model Context Protocol (MCP) gateway, which then executes it through MCP tools. At no point is the metadata validated, allowing attackers to bypass security boundaries without exploiting traditional software bugs.

### The Attack Vector 🛡️

At the core of DockerDash is what Noma Labs called **Meta-Context Injection**. The MCP gateway is designed to pass contextual information to large language models, but it cannot distinguish between descriptive metadata and pre-authorized internal instructions. By embedding commands inside seemingly harmless Docker LABEL fields, attackers can manipulate the AI's reasoning and turn context into action.

### Impact Assessment ⚠️

The impact varies by environment but remains severe in both cases:
- **Remote Code Execution (RCE)** through Docker CLI commands in cloud or local CLI setups.
- Exposure of container configurations, environment variables, and network settings.
- Enumeration of installed MCP tools, images, and system configuration data.

In Docker Desktop, attackers can also exfiltrate collected data by instructing Ask Gordon to embed it into outbound requests, bypassing controls focused on command execution rather than unauthorized reads.

### Response from Docker 🛠️

Noma Labs reported the issue to Docker on September 17, 2025. Docker confirmed the vulnerability on October 13 and addressed it in Docker Desktop version 4.50.0, released on November 6, 2025. Public disclosure followed earlier today. Docker implemented two key mitigations:
- Ask Gordon no longer renders user-provided image URLs, blocking one exfiltration path.
- It now requires explicit user confirmation before invoking any MCP tools, introducing a human-in-the-loop safeguard.

**Users are strongly advised to upgrade to Docker Desktop 4.50.0 or later to reduce exposure to this new class of AI-driven supply chain attacks.**

To read the complete article see:
[Read full article](https://www.infosecurity-magazine.com/news/dockerdash-weakness-dockers-ask/)