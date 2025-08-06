---
title: Cursor IDE Persistent Code Execution via MCP Trust Bypass
date: 2025-08-05
categories: [SECURITY]
tags: [RCE,CURSOR IDE,VULNERABILITY,CHECK POINT]
---

**Key Insights**

Critical RCE Flaw in Popular AI-powered IDE.

Check Point Research uncovered a persistent remote code execution vulnerability in Cursor, a fast-growing AI-powered coding platform trusted by developers worldwide.

**MCP Vulnerability**  
Cursor allows attackers to gain long-term, silent access to developer environments by altering previously approved Model Context Protocol (MCPs), with no additional user prompt.

**Real-World Attack Scenario**  
In shared repositories, a benign-looking MCP configuration can be weaponized after approval, triggering malicious code execution every time a project is opened in Cursor.

**Broader AI Supply Chain Risk**  
The flaw exposes a critical weakness in the trust model behind AI-assisted development environments, raising the stakes for teams integrating LLMs and automation into their workflows.

To read the complete article, see:  
[Cursor IDE: Persistent Code Execution via MCP Trust Bypass](https://blog.checkpoint.com/research/cursor-ide-persistent-code-execution-via-mcp-trust-bypass/)  
Also here:  
[Cursor Vulnerability - MCPoison](https://research.checkpoint.com/2025/cursor-vulnerability-mcpoison/)